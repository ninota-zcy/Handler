# Handler
handler
使用Handler更新用户界面。一般而言有两种方法
Handler的主要用法是在新线程中发送消息，然后在主线程中处理消息
也可以使用Handler的post()方法将Runnable对象从后台线程发送给主线程

通过Hander.sendMessage(Message)将消息发送给主线程，在主线程Handler.handleMessage()中接收并处理该消息

直接用new Handler()会出现Handler Leak的警告。通过网上的搜索，得到一个简便的解决方法。
  final Handler handler = new Handler(new Handler.Callback() {
            @Override
            public boolean handleMessage(Message msg) {
                // TODO Auto-generated method stub
                textview.setText(msg.arg1+"");
                return false;
            }
        }) ;
