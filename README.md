# Hello-world
Practise my OC skill.


-(NSString *)getStringWithPattern:(NSString *)originalString :(NSString *)pattern
{
    if (originalString == nil || pattern == nil)
    {
        return nil;
    }
    NSString *str=nil;
    
    NSRegularExpression *regExp=[NSRegularExpression regularExpressionWithPattern:pattern options:NSRegularExpressionCaseInsensitive error:NULL];
    @try {
        NSArray *matches =[ regExp matchesInString:originalString options:0 range:NSMakeRange(0, [originalString length])];
        
        for (NSTextCheckingResult *match in matches) {
            NSRange firstHalfRange = [match rangeAtIndex:1];
            str = [originalString substringWithRange:firstHalfRange];
            break;
        }
    }
    @catch (NSException *exception) {
        
        NSLog(@"<Exception> getStringWithPattern");
    }
    return str;
}
