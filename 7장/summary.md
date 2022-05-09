:ghost: kotlin 7장 정리 :ghost:
=============
### 하면서 막혔던 점 
-------------
Extensions.kt을 잘못하고 class로 만들어서 코드 짜다가 오류 난 정도
### 추가해본 기능
-------------
모소 수업 시간에 배운 커스텀 어댑터를 사용해보고 싶어서 개발자 정보 메뉴에 id가 action_address인 item 연락처를 추가했고 layout 파일에 activity_main.xml, custom_list_item.xml를 만들었다 activity_main.xml에는 listView만 들어가고, custom_list_item.xml에는 화면에 보여질 리스트 형태를 만듬.(밑에 사진 처럼)<br>
<img src="https://user-images.githubusercontent.com/78543382/167379363-1ab0cd3b-37c2-4954-9534-670c8ef75d38.png"/> <br>
커스텀 어댑터를 적용하기 위해 AddressListView, ListViewAdapter, ListViewItem, MainActivity 클래스를 만듬<br>
1.AddressListView <br>
<pre>
<code>
package com.example.mywebbrowser

import ListViewAdapter
import android.os.Bundle
import android.widget.ListView
import androidx.appcompat.app.AppCompatActivity
import com.example.mywebbrowser.databinding.ActivityItemBinding

class AddressListView : AppCompatActivity() {
    var list = arrayListOf<ListViewItem>(
        ListViewItem("J", "1234"),
        ListViewItem("S", "2345"),
        ListViewItem("K", "3456"),
        ListViewItem("L", "4567")
    )


    private val binding by lazy {
        ActivityItemBinding.inflate(layoutInflater)
    }
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(binding.root)

        val listAdapter = ListViewAdapter(this, list)
        val listView = findViewById<ListView>(R.id.listView)
        listView.adapter = listAdapter
    }
}
</code>
</pre> <br>
2. ListViewAdapter<br>
<pre>
<code>

import android.content.Context
import android.view.LayoutInflater
import android.view.View
import android.view.ViewGroup
import android.widget.BaseAdapter
import android.widget.TextView
import com.example.mywebbrowser.ListViewItem
import com.example.mywebbrowser.R

class ListViewAdapter(val context: Context, val items: ArrayList<ListViewItem>): BaseAdapter() {
    override fun getCount(): Int {
        return items.size
    }
    override fun getItem(position: Int): Any{
        return items[position]
    }
    override fun getItemId(position: Int): Long {
        return 0
    }
    override fun getView(position: Int, view: View?, parent: ViewGroup?): View {
        val view: View = LayoutInflater.from(context).inflate(R.layout.custom_list_item, null)

        val Name = view.findViewById<TextView>(R.id.tvName)
        val Phone = view.findViewById<TextView>(R.id.tvPhone)
        val list = items[position]
        Name.text = list.name
        Phone.text = list.phone

        return view
    }
}
</code>
</pre> <br>
3. ListViewItem
<pre>
<code>
package com.example.mywebbrowser

class ListViewItem(val name: String, val phone: String){
}
</code>
</pre><br>
4. MainActivity에서 수정한 부분
<pre>
<code>
            R.id.action_address -> {
                val intent = Intent(this, AddressListView::class.java)
                startActivity(intent)
                return true
            }
</code>
</pre> <br>
### 실행결과
-------------
<img src="https://user-images.githubusercontent.com/78543382/167381071-229c8615-6b80-4d12-94ef-a38b1d6d26ca.png"/> <br>
리스트에 저장한게 다 나와야하는데 하나만 나와서 천천히 코드 다시 보고 수정해야할듯






