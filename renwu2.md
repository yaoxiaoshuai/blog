#一：基础命令
###1.1移动光标

>             ^
             k              提示︰ h 的鍵位于左邊，每次按下就會向左移動。
	            < h       l >               l 的鍵位于右邊，每次按下就會向右移動。
		                 j                     j 鍵看起來很象一支尖端方向朝下的箭頭。
				              v
					      >1.  h 左
					      1. j
					      1. k 下
					      1. l  右

					      ###1.2进入和退出

					      >退出
					      > >ESC进入正常模式  然后输入
					      >>1. 输入:q! <回车> 修改保存
					      1. 输入:wq! <回车> 修改保存

					      >vim的进入
					      >>1.vi  fileName
					      2.vim fileName

					      ###1.3删除字符
					      >正常模式下
					      >>删除单个字符  x

					      ###1.4插入
					      > 当前字符前进入插入模式 i

					      ###1.5撤销类命令
					      >u撤销最后命令,U修正一整行
					      `CTRL-R (先按下 CTRL 鍵不放開，接著輸入 R 鍵) ，這樣就可以執行恢復命令，也就是撤消掉撤消命令。`

					      ###2.1删除类命令
					      >1.删除单个字符x
					      2.删除至当前单词结束 dw
					      3.删除到当前行尾 d$

					      ###2.2 命令格式
					      > `[number]   d   object      或者     d   [number]   object`
					      number代表次数，d代表删除，object代表删除对象
					      >
					      删除对象列表:
					      >>`w - 從當前光標當前位置直到單字/單詞末尾，包括空格。`
					      `e - 從當前光標當前位置直到單字/單詞末尾，但是 *不* 包括空格。`
					      `$ - 從當前光標當前位置直到當前行末`
					      >单独输入w、e、s时光标会做相对应的移动

					      ###2.3对象命令的特殊情况
					      >`输入dd可以删除当前行,2dd删除两行`


					      ---
					      ###三:替换类命令
					        >1. 要重新置入已經刪除的文本內容，請輸入小寫字母 p。該操作可以將已刪除的文本內容置于光標之後。如果最後一次刪除的是一個整行，那麼該行將置于當前光標所在行的下一行。2. 要替換光標所在位置的字符，請輸入小寫的 r 和要替換掉原位置字符的新字符即可。
						3. 更改類命令允許您改變指定的對象，從當前光標所在位置直到對象的末尾。 比如輸入 cw 可以替換當前光標到單詞的末尾的內容；輸入 c$ 可以替換當前光標到行末的內容。
						4. 更改類命令的格式是︰
						         [number]   c   object        或者      c   [number]   object
							 `cw c$ `

							 ---
							 ##4.定位以及搜索
							   >1. Ctrl-g 用于顯示當前光標所在位置和文件狀態信息。Shift-G 用于將光標跳
							        轉至文件最後一行。先敲入一個行號然後按 Shift-G 則是將光標移動至該行
								     號代表的行。

								       >2. 輸入 / 然後緊隨一個字符串是則是在當前所編輯的文檔中向後查找該字符串。
								            輸入問號 ? 然後緊隨一個字符串是則是在當前所編輯的文檔中向前查找該字
									         符串。完成一次查找之後按 n 鍵則是重復上一次的命令，可在同一方向上查
										      找下一個字符串所在；或者按 Shift-N 向相反方向查找下該字符串所在。

										        >3. 如果光標當前位置是括號(、)、[、]、{、}，按 % 可以將光標移動到配對的
											     括號上。

											       >4. 在一行內替換頭一個字符串 old 為新的字符串 new，請輸入  :s/old/new
											            在一行內替換所有的字符串 old 為新的字符串 new，請輸入  :s/old/new/g
												         在兩行內替換所有的字符串 old 為新的字符串 new，請輸入  :#,#s/old/new/g
													      在文件內替換所有的字符串 old 為新的字符串 new，請輸入  :%s/old/new/g
													           進行全文替換時詢問用戶確認每個替換需添加 c 選項，請輸入 :%s/old/new/gc


														   ---
														   ##五︰在 VIM 內執行外部命令的方法

														     >1. :!command 用于執行一個外部命令 command。
														          >>請看一些實際例子︰
															           :!dir          -  用于顯示當前目錄的內容。
																            :!rm FILENAME  -  用于刪除名為 FILENAME 的文件。

																	      >2. :w FILENAME  可將當前 VIM 中正在編輯的文件保存到名為 FILENAME的文件中。

																	        >3. :#,#w FILENAME 可將當前編輯文件第 # 行至第 # 行的內容保存到文件FILENAME 中。

																		  >4. :r FILENAME 可提取磁盤文件 FILENAME 並將其插入到當前文件的光標位置後面。

																		  ---
																		  ##六：其他插入及替换方式
																		    >1. 輸入小寫的 o 可以在光標下方打開新的一行並將光標置于新開的行首，進入插入模式。
																		         輸入大寫的 O 可以在光標上方打開新的一行並將光標置于新開的行首，進入 插入模式。

																			   >2. 輸入小寫的 a 可以在光標所在位置之後插入文本。 輸入大寫的 A 可以在光標所在行的行末之後插入文本。

																			     >3. 輸入大寫的 R 將進入替換模式，直至按 <ESC> 鍵退出替換模式而進入正常模式。

																			       >4. 輸入 :set xxx 可以設置 xxx 選項。

																			       ---
																			       ##七：光标定位类汇总

																			       >w - 從當前光標當前位置直到單字/單詞末尾，包括空格。
																			       e - 從當前光標當前位置直到單字/單詞末尾，但是 *不* 包括空格。
																			       $ - 從當前光標當前位置直到當前行末
																			       （- 跳到段首 
																			       ）-跳到段尾     
																			       % -对应括号位置
																			       `.etc`

																			       ---
																			       ##八：复制类命令

																			       > 1.  yy  复制行  y5y    复制5行
																			       2. yl  复制字符  y5l   复制5个字符
																			       3. yw 复制单词    y5w 复制五个单词
																			       `.etc` 


																			       ---
																			       ##九：作业相关
																			       > 跳到段首 （
																			       跳到段尾     ）
																			       复制yy   `复制10行y10y`
																			       粘贴 p   
																			       删除一行 dd   `删除两行d2d`
																			        向下翻页  ctrl+f 
																				 向上翻页  ctrl+b 
																				 10 shift+g  或者 :10  跳到固定行(此时是第十行)
																				 ：/strName  查找strName  此时可以按N或者shift+n表示向上或向下查找下一个
