# MSHTMLImg
UILabel加载html点击查看大图
demo
   UILabel *nn = [UILabel labelFrame:CGRectMake(10, 100, SCREEN_WIDTH-2*10, 40) font:14 tx:@"" txColor:[UIColor blackColor] alien:0];
    nn.numberOfLines = 0;
    [self.view addSubview:nn];
    NSString *path = [[NSBundle mainBundle] pathForResource:@"warning@2x" ofType:@"png"];
    NSLog(@"path %@",path);
    NSString *s0 = [NSString stringWithFormat:
    @"<p><img src=\"file:///%@\" width=\"300\" ></p>"
    @"<p>这是第一张图片</p>"
    @"<p><img src=\"https://profile-avatar.csdnimg.cn/default.jpg\" width=\"300\" ></p>"
    @"<p>这是第二张图片这是第二张图片这是第二张图片这是第二张图片这是第二张图片这是第二张图片这是第二张图片</p>"
    @"<p><img src=\"https://img.php.cn/upload/article/202105/19/2021051916102744441.jpg\" width=\"300\" ></p>",path];
    NSMutableAttributedString *att =  [[NSMutableAttributedString alloc] initWithData:[s0 dataUsingEncoding:NSUnicodeStringEncoding] options:@{NSDocumentTypeDocumentAttribute: NSHTMLTextDocumentType} documentAttributes:nil error:nil];
    att.yy_lineSpacing = 5;
//    [att addAttribute:NSFontAttributeName value:[UIFont systemFontOfSize:15] range:NSMakeRange(0, att.length)];

    nn.attributedText = att;
