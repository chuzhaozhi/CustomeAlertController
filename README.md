# CustomeAlertController
一个简单实用的自定义可输入弹窗效果
具体使用方法如下：
-(void)clickDeleteButton:(UIButton *)sender{
    CustomAlertController *customAlertController = [[CustomAlertController alloc] initWithConfirmAction:^(NSString *inputText) {
            NSLog(@"%@",inputText);//  获取输入的内容
        if (inputText.length<=0){
            return; //  如果未输入则返回
        } else{ //  有输入内容进行相应的操作
            [self deleteApplicationWithPassword:inputText];
        }
    } andCancelAction:^{
    //  取消按钮的事件
    }];
    [self presentViewController:customAlertController animated:YES completion:nil]; //  present这个自定义视图
}
