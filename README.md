# YTKExample
对 YTKNetworking 请求头封装
1.首先创建一个继承于YTKBaseRequest 的请求类，然后在初始化-(instancetype)initWithArguments:(NSDictionary *)arguments Url:(NSString * )url Type:(YTKRequestMethod)type方法实现中，将需要添加的请求头参数进行操作，比如添加到字典里一些特定要求的参数，比如APPID 等一些必须参数
2.然后重写- (NSDictionary<NSString *, NSString *> *)requestHeaderFieldValueDictionary；方法，返回刚刚已经添加过需要信息的字典；
3.重写返回 url 与请求体里面需要追加的参数，如下：
- (NSString *)requestUrl {
    return _url;
}
- (YTKRequestMethod)requestMethod {
    return _type;
}
4.有需要可以在这里重写请求网络数据方法-(void)beginWithCompletionBlockWithSuccess:(YTKRequestCompletionBlock)success failure:(YTKRequestCompletionBlock)failure；
在里面做信息处理的操作。
