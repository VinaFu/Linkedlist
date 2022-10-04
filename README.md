# Linkedlist

1） 定义class的方法：用def __init__(self):
如果有变量的话，就定义在括号里面，没有的话就不用了。

      class node:
          def __init__(self, data=None):

      后面的每次引用都用self.对方：
      def __init__(self, data=None):
              self.data = data
              self.next = None
        
2）和array的区别：快速加减新的变量时间为O（1）；而array为O（n）.      


3）自己写一个linkedlist：

        class node:                 建立一个单独node，有数据，连下一个，目前连不上，所以是none
            def __init__(self, data=None):
                self.data = data
                self.next = None

        class linked_list:          开头第一个作为head
            def __init__(self):
                self.head = node()

            def append(self,data):  
                new_node = node(data)    //新建一个车厢
                cur = self.head          //第一个为head
                while cur.next!=None:    //当有下一个的时候：cur.next！=none，连到下一个
                    cur = cur.next
                cur.next = new_node     //下一个相当于新的

            def length(self):
                cur = self.head
                total = 0
                while cur.next != None:
                    total +=1
                    cur = cur.next
                return total 

            def display(self):
                elems = []
                cur_node = self.head
                while cur_node.next!=None:
                    cur_node=cur_node.next
                    elems.append(cur_node.data)
                print (elems)

            def get(self, index):
                if index>=self.length():
                    print("ERROR: 'Get' Index out of range!")
                    return None
                cur_index=0
                cur_node=self.head
                while True:
                    cur_node=cur_node.next
                    if cur_index==index: 
                        return cur_node.data
                    cur_index+=1

            def erase(self, index):
                if index>=self.length():
                    print("ERROR: 'Erase' Index out of range!")
                    return
                cur_index=0
                cur_node=self.head
                while True:
                    last_node = cur_node        （连上一个）
                    cur_node = cur_node.next    （连下一个）
                    if cur_index==index: 
                        last_node.next = cur_node.next    （让他们等同起来）
                        return 
                    cur_index+=1
 

my_list = linked_list()

my_list.append(0)
my_list.append(1)
my_list.append(2)
my_list.append(3)
my_list.append(4)

# print (my_list.get(4))
my_list.erase(2)
my_list.display()


加的其他功能：

           def getMidVal1(self):
              long=self.length()
              mid=[]
              if self.length()%2==0:
                  mid.append(self.get(long/2))
              else:
                 mid.append(self.get((long-1)/2))
              print(mid)
      # 5->NULL
      # The middle element is [5] ||  [5]
      # 4->5->NULL   
      # The middle element is [5] ||  [4,5]
      # 3->4->5->NULL
      # The middle element is [4] ||  [4]
      # 2->3->4->5->NULL
      # The middle element is [4] ||  [3,4]
      # 1->2->3->4->5->NULL
      # The middle element is [3] ||  [3]


          def getMidVal2(self):
              long=self.length()
              mid=[]
              if self.length()%2==0:
                  mid.append(self.get(long/2-1))
                  mid.append(self.get(long/2))
              else:
                  mid.append(self.get((long-1)/2))
              print(mid)

      # 去加個getMiddleValue() 取中間node 的值 、 list 是偶數就取 中間兩個

      my_list = linked_list()
      my_list.append(1)
      my_list.append(2)
      my_list.append(3)
      my_list.append(4)
      my_list.append(5)

      # # print (my_list.get(4))
      # my_list.erase(2)
      print("Method 1:")
      my_list.getMidVal1()
      print("Method 2:")
      my_list.getMidVal2()
      print("Original Input: ")
      my_list.display()
              
              
  
