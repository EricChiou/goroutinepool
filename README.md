# goroutine-pool
## How to use
<pre><code>package main  
  
import (  
	"github.com/EricChiou/goroutinepool"  
)  
  
func main() {  
&nbsp;&nbsp;&nbsp;&nbsp;pool := goroutinepool.New(5) // new gorotine pool has 5 gorotine  
&nbsp;&nbsp;&nbsp;&nbsp;for i := 0; i < 1000; i++ {  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;pool.Add(1)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;go func(i int) {  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;fmt.Println("gorotine ", i)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;pool.Done()  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}(i)  
&nbsp;&nbsp;&nbsp;&nbsp;}  
&nbsp;&nbsp;&nbsp;&nbsp;pool.Wait()  
}</code></pre>