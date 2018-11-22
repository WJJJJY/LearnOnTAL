DLL的灾难

人们将不同版本DLL混合造成的不一致性形象的称为 “动态连接库的地狱“(DLL Hell) ，甚至微软自己也这么说(http://msdn.microsoft.com/library/techart/dlldanger1.htm)。 

如果你的程序使用你自己的DLL时请注意： 

　　不能将debug和release版的DLL混合在一起使用。debug都是debug版，release版都是release版。 

　　解决办法是将debug和release的程序分别放在主程序的debug和release目录下