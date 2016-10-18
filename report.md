#Cbenchのボトルネック調査
今回はruby-profを用いてプログラムの解析を行う．
まずは基本的なプログラムである./lib/cbench.rbを解析する．
このプログラムは単純にpacket_inハンドラの中に，flow_modを追加する内容が記述されている．
このプログラムによって追加されたパケットの返送設定によって返送されたパケットの数がcbenchによってカウントされることとなる．

まず，タスクの稼働方法は
'ruby-prof -p call_stack -f call_stack.html ~/.rvm/gems/ruby-2.2.1/bin/trema run ./lib/cbench.rb'
となる．call_stackという出力方法により，html形式で解析しやすくした．
その結果が次のようになる．
![cbench.rbの解析結果](./cbench.rb)


#Cbenchの高速化

