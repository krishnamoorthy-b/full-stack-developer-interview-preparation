# java interview questions
1) Can print before invoke main method?
<details>
  <summary>Answer</summary></br>
  Using static block we can print before main and it will be invoked only once when class getting load.</br>
  
  ```
    class HelloWorld {
      static{
          System.out.print("hi ");
      }
      public static void main(String[] args) {
          System.out.print("krishna");
      }
    }
  ```
  
  **Output**
  hi krishna
</details>

2) Static vs Instance block
<details>
  <summary>Answer</summary></br>
  <table>
    <thead>
      <tr>
        <th>Static Block</th>
        <th>Instance Block</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>It will be getting invoked once when class load</td>
        <td>It will be getting invoked each time when create instance of class</td>
      </tr>
      <tr>
        <td>Used for initialize static variable and invoke static methods</td>
        <td>Used for initialize instance variable and instance methods</td>
      </tr>
    </tbody>
  </table>
</details>

3) Which object is eligible for garbage collection?

<details>
<summary>Answer</summary></br>
<ul>
  <li>Reasigning Reference variable</li>
  <li>Nullifying Reference variable</li>
  <li>Ananymous object</li>
  <li>Create Object inside a method</li>
</ul>
</details>

4) How to mannually trigger garbage collection?

<details>
<summary>Answer</summary></br>
System.gc()
</details>

5) Final vs Finally vs Finalize

<details>
  <summary>Answer</summary></br>
  <table>
    <thead>
      <tr>
        <th>Final</th>
        <th>Finally</th>
        <th>Finalize</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>It's a constant. We can use this for variable, method and class.</td>
        <td>It's a block and used for try catch use case. This block will be called always.</td>
        <td>It's a method and it will called when before objected is garbage collected.</td>
      </tr>
    </tbody>
  </table>
</details>

6) Exception vs Error
7) Checked vs UnChecked exception
8) What is try with resource?
9) throw vs throws
10) ArrayList vs LinkedList
11) What is HashTable?
12) HashMap vs HashSet
13) Fail safe vs Fail fast
14) Comparator vs Comparable
15) Consumer vs Producer
16) Diamond problem in java?
17) How to create thread?
18) What and all ways stop main thread?
19) What is cuncurrent modification exception?
20) When dead lock will occur?
21) How to achieve parallel threading?
22) What is join, sleep, and yeild?
<details>
<summary>Answer</summary>

**Join** used for wait one thread until finish another thread. In below example t2 is waiting for t1 until it's complete.<br>
**Sleep** used for just pause current thread until time ends and it's not bother another thread.<br>
**Yeild** It's denoting current thread isn't important and run if any thread equal or higher priority with runnable state than current thread, otherwise continue current thread. <br>
  
  ```
   import java.util.*;

    public class Practice {
        public static void main(String[] args) throws Exception {
            // Parallel threading
            //Thread 1
            Thread t1 = new Thread() {
                public void run(){
                    for(int i=0;i<5;i++){
                            try{
                                System.out.println(Thread.currentThread().getName() + "->" + i);
                                // Every iteration t1 thread alone get into sleep mode where as t2 thread will execute immediately
                                Thread.sleep(100);
                            } catch(InterruptedException e){
                                e.printStackTrace();
                            }
                    }
                }
            };
            t1.start();
            // t2 will wait until t1 completes
            t1.join();
           
            //Thread 2
            Thread t2 = new Thread() {
                public void run(){
                    for(int i=0;i<5;i++){
                        System.out.println(Thread.currentThread().getName() + "->" + i);
                    }
                }
            };
            t2.start();
        }
    }

  ```
  **Output**
  ```
  Thread-0->0
  Thread-0->1
  Thread-0->2
  Thread-0->3
  Thread-0->4
  Thread-1->0
  Thread-1->1
  Thread-1->2
  Thread-1->3
  Thread-1->4
  ```
</details>
23) What is ExecutorService and it's type?
