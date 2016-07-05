# 控制层介绍

控制层是用来接受不同的Ajax请求的，平台采用了SpringMVC实现，控制器Controller 负责处理由DispatcherServlet 分发的请求，它把用户请求的数据经过业务处理层处理之后封装成一个Model ，然后再把该Model 返回给对应的View 进行展示。在SpringMVC 中提供了一个非常简便的定义Controller 的方法，你无需继承特定的类或实现特定的接口，只需使用@Controller 标记一个类是Controller ，然后使用@RequestMapping 和@RequestParam 等一些注解用以定义URL 请求和Controller 方法之间的映射，这样的Controller 就能被外界访问到。

```
/**
 * spring MVC控制类示例，开发者需要在此基础上进行修改，适应项目的需求
 */
@RestController
@RequestMapping(value = "/goods")
public class GoodJdbcDemoController {
	private final Logger logger = LoggerFactory.getLogger(getClass());
	
	@Autowired
	private GoodJdbcDemoService goodService;
	
	@RequestMapping(value="/page", method= RequestMethod.GET)
	public @ResponseBody Object page(@RequestParam(value = "pageIndex", defaultValue = "0") int pageNumber, @RequestParam(value = "pageSize", defaultValue = "10") int pageSize, @RequestParam(value = "sortType", defaultValue = "auto") String sortType, Model model, ServletRequest request) {
		Map<String,Object> result = new HashMap<String,Object>();
		Map<String, Object> searchParams = new HashMap<String, Object>();
		searchParams = Servlets.getParametersStartingWith(request, "search_");
		PageRequest pageRequest = buildPageRequest(pageNumber, pageSize, sortType);
		try {
			Page<GoodJdbcDemo> accountPage = goodService.getDemoPage(searchParams, pageRequest);
			result.put("data", accountPage);
			result.put("flag", "success");
			result.put("msg", "查询数据成功!");
		} catch (Exception e) {
			String errMsg = "查询数据详情失败!";
			result.put("flag", "fail");
			result.put("msg", errMsg);
			logger.error(errMsg, e);
		}
		return result;
	}
    ......
  }
```


### 使用 URI 模板

   URI 模板就是在URI 中给定一个变量，然后在映射的时候动态的给该变量赋值。如URI 模板http://localhost/app/{variable1}/index.html ，这个模板里面包含一个变量variable1 ，那么当我们请求http://localhost/app/hello/index.html 的时候，该URL 就跟模板相匹配，只是把模板中的variable1 用hello 来取代。在SpringMVC 中，这种取代模板中定义的变量的值也可以给处理器方法使用，这样我们就可以非常方便的实现URL 的RestFul 风格。这个变量在SpringMVC 中是使用@PathVariable 来标记的。
   在SpringMVC 中，我们可以使用@PathVariable 来标记一个Controller 的处理方法参数，表示该参数的值将使用URI 模板中对应的变量的值来赋值。
   
   ```
@Controller  
@RequestMapping ( "/goods/{variable1}" )  
public class GoodJdbcDemoController {  
  
    @RequestMapping ( "/showView/{variable2}" )  
    public ModelAndView showView( @PathVariable String variable1, @PathVariable ( "variable2" ) int variable2) {  
       ModelAndView modelAndView = new ModelAndView();  
       modelAndView.setViewName( "viewName" );  
       modelAndView.addObject( " 需要放到 model 中的属性名称 " , " 对应的属性值，它是一个对象 " );  
       return modelAndView;  
    }  
}   
   ```
