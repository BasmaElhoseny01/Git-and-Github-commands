```cpp
//
// Created by Dell on 9/29/2022.
//

# include <bits/stdc++.h>
using namespace std;

int main() {
    //======================================================= 1.Vector ===================================================================
    //#include <vector>

    // Elements of the same type [like array]

    /**Notes:
     * 1.define vectors and arrays of large size outside main so it is stored in the heap not stack so we have faster acessing time
     **/

    // 1.1 Decleration
    vector<int> v;              // empty vector size=0
    vector<int> v2(5);          // vector<int>name(size)
    vector<int> v3(10, 0);      // vector<int>name(size,initial values)  0 0 0 0 0 0 0 0 0 0 0 0 0
    vector<int> v4 = {1, 2, 3}; // initialize vector with elements, size=3    1 2 3

    // 1.2 Accessing element =>Random access
    cout << v3[0];

    // Note:
    // v2 inital values here are 0 opposite to array(garbage)
    for (int i = 0; i < v2.size(); i++)
        cout << v2[i] << " "; // 0 0 0 0 0

    cout << endl;
    // but remember array garbage
    int arr[5];
    for (int i = 0; i < 5; i++)
        cout << arr[i] << " "; // 11929464 0 1218947718 32761 5131688 0

    // 1.3 size
    /*
    -Returns the number of elements in the vector.
    -Complixity:Constant
    -return:size_type
    */
    cout << endl << v.size();//0

    // 1.4 resize
    //   vector<int> v2(5);
    cout << endl;
    v2.resize(10); // size 5
    cout << v2.size(); //10
    // v2d[0].size()=5; //error

    // 1.5 empty
    /*
    -Returns whether the vector is empty
    -Complexity:Constant
    -return: true or false
    */
    cout << endl << v.empty(); //1

    // 1.6 push_back
    /*
    -push element after last element
    -Complexity:Constant (amortized time, reallocation may happen).If a reallocation happens,
     the reallocation is itself up to linear in the entire size.
    -return:none
    */
    v.push_back(1);

    // 1.7 pop_back
    /*
    -remove last element
    -Complexity:Constant.
    -return:none
    */
    v.pop_back();

    // 1.8 looping over vector
    v.push_back(4);
    v.push_back(5);
    v.push_back(3);
    v.push_back(4);

    // a.using for loop
    cout << endl;
    for (int i = 0; i < v.size(); i++) {
        cout << v[i] << " "; // 4 5 3 4
    }

    // b.simply
    cout << endl;
    // Note:i here is the element itself not index , i here isn't an iterartot
    for (auto i: v) {
        cout << i << " "; // 4 5 3 4
    }

    // c.iterator
    vector<int>::iterator it; // iterator of type vector<int>iterator
    cout << endl;
    for (it = v.begin(); it != v.end(); it++)
        cout << *it << " "; // 4 5 3 4

    // Note: V= 4 5 3 4
    cout << endl;
    for (auto i: v) {
        i = 5;
    }
    for (int i = 0; i < v.size(); i++)
        cout << v[i] << " "; // 4 5 3 4 no change ==> to make change use & as below

    for (auto &i: v)
        i = 5;
    cout << endl;
    for (int i = 0; i < v.size(); i++)
        cout << v[i] << " "; // 5 5 5 5  ==> changed

    // 1.8 front and back
    /* front same for back
    -Returns a reference to the first element in the vector.Unlike member vector::begin, which returns an iterator to
     this same element, this function returns a direct reference.
    -Complexity:Constant.
    -return:A reference to the first element in the vector container.
    */
    // v4:1, 2, 3
    cout << endl;
    cout << v4.front(); // 1
    cout << endl;
    cout << v4.back(); // 3

    // 1.9 clear
    /*
    -Removes all elements from the vector (which are destroyed), leaving the container with a size of 0.
    -complexity:O(N) where N is the size of the vector.
    -return:none
    */
    cout << endl;
    v4.clear();
    cout << v4.size(); // 0

    // 1.10 2D vector
    //****VIP define outsize main to use heap not stack ==> faster
    cout << endl;
    // a.array of vectors
    vector<int> v2d[10]; // v[0]=>vector<int>   v[1]=>vector<int>

    // b.vector of vector
    vector<vector<int>> v2d2(5);                     // row=5
    vector<vector<int>> v2d3(5, vector<int>(10, 0)); // row= 5*10 of 0
    cout << v2d3[0][0] << endl;


    //1.11 vector::operator=
    //    vectorname1 = (vectorname2)
    //            Parameters :
    //    Another container of the same type.
    //            Result :
    //    Assign the contents of the container passed as
    //    parameter to the container written on left side of the operator.
    //Complexity: Linear O(N)
    vector<int> myvector1{ 1, 2, 3 };
    vector<int> myvector2{ 3, 2, 1, 4 };
    myvector1 = myvector2;
    cout << "myvector1 = ";
    for (auto it = myvector1.begin(); it != myvector1.end(); ++it)
        cout << ' ' << *it;
    //myvector1= 3 2 1 4

    //======================================================= 2.Queue ==================================================
    //#include <queue>
    // FIFO

    /**Notes:
     * no random access
     **/

    // 2.1 Decleration
    queue<int> q;

    //2.2 push
    /*
    -Inserts a new element at the end of the queue, after its current last element. The content of this new element is
     initialized to val.
    -Complixity:constant
    -return:none
    */
    q.push(5);
    q.push(8);
    q.push(10);
    // q:5 8 10

    //2.3 pop (removes front element)
    /*
    -Removes the next element in the queue, effectively reducing its size by one
    -Complexity:Constant
    -Return:none
    */
    q.pop(); // q:8 10

    //2.4 size
    /*same as vector*/
    cout << q.size() << endl; // 2

    //2.5 empty
    /*same as vector*/
    cout << q.empty() << endl; // 0

    //2.6 Acessing element =>front only
    /*
    -Returns a reference(direct) to the next element in the queue.
    -return:A reference to the next element in the queue.
    -Complexity:Constant
    */
    cout << q.front() << endl; // 8

    //======================================================= 3.Stack ==================================================
    // LIFO
    //#include <stack>

    //3.1 Decleration
    stack<int> s;

    //3.1 push
    /*
    -Inserts a new element at the top of the stack, above its current top element.
    -Complixity:constant
    -return:none
    */
    s.push(10);
    s.push(20);
    s.push(30);
    s.push(40);
    // 40 30 20 10

    //3.3 pop
    /*
    -Removes the element on top of the stack, effectively reducing its size by one.
    -Complixity:constant
    -return:none
    */
    s.pop(); // s: 30 20 10

    //3.4 size
    /*same as vector*/
    cout << s.size() << endl; // 3

    //3.5 empty
    /*same as vector*/
    cout << s.empty() << endl; // 0

    //3.6 Acessing element =>top only
    /*
    -Returns a reference to the top element in the stack.
    -Complexity:Constant
    -return:A reference to the top element in the stack.
    */
    // s:30 20 10
    s.top(); // 30

    //======================================================= 4.Deqeue =================================================
    //#include <deque>

    // Queue+Stack
    // push in last or begin dequeu from begin and end
    // Like Vcetor but in extra it has push_front while vector doesn't

    // Basics:
    //  Insertion or removal of elements at start or end- O(1)
    //  Accessing Elements- O(1)

    //4.1 Deceleration
    deque<int> dq;

    //4.2 push_front
    /*
   -Inserts a new element at the beginning of the deque container, right before its current first element.
   -return:none
   -Complexity:Constant
   */
    dq.push_front(10); //dq: 10

    //4.3 push_back
    /*
    -Adds a new element at the end of the deque container, after its current last element.
    -Complexity&return:same as push_front
    */
    dq.push_back(12); //10 12

    //4.4 pop_front
    /*
    -Removes the first element in the deque container, effectively reducing its size by one
    -Complexity&return:same as push_front
    */
    dq.pop_front();//dq:12

    //4.5 pop_back
    /*
    -Removes the last element in the deque container, effectively reducing the container size by one.
    -Complexity&return:same as push_front
    */
    dq.pop_back(); //dq:

    //4.6 size
    /*same as vector*/
    cout << dq.size() << endl; // 0

    //4.7 empty
    /*same as vector*/
    cout << dq.empty() << endl; // 1


    //4.6 acessing elemets (front - back - random access) O(1)
    dq.push_front(1);
    dq.push_front(2);
    dq.push_front(3);
    //dq:3 2 1

    cout << dq.front() << " "; //3
    cout << dq.back() << " "; //1
    cout << dq[1] << " ";//2


    //======================================================= 5.Priority queue =========================================
    // #include<queue>

    //ordered queue descending
    //implemented Heap min and max

    //5.1 Declaration
    priority_queue<int> pq;//by default descending max ..... min

    //5.2 push
    /*
    -Inserts a new element in the priority_queue.
    -Complexity:O(log n) ,n is current size
    -return:none.
    */
    pq.push(5);
    pq.push(10);
    pq.push(1);
    //pq:10 5 1

    priority_queue<int> temp;
    cout << endl;
    //loop over pq
    while (!pq.empty()) {
        int x = pq.top();
        temp.push(x);
        cout << x << " ";
        pq.pop();
    }
    cout << endl;
    pq = temp;
    //5.3 pop
    /*
    -Removes the element on top of the priority_queue, effectively reducing its size by one.
    -Complexity:O(log n) ,n is current size
    -return:none.
    */
    pq.pop(); //pq:5 1


    //5.4 top
    /*
    -The top element is the element that compares higher in the priority_queue.
    -Complexity:O(1)
    -return:A reference to the top element in the priority_queue.
    */
    cout << pq.top() << endl;//5

    //5.5 size
    /*same as vector*/
    cout << pq.size() << endl;//2

    //5.6 empty
    /*same as vector*/
    cout << pq.empty() << endl;//0

    //5.7 Priority queue in ascdening  min ..... max
    priority_queue<int,vector<int>,greater<>>minpq;
//    priority_queue<int,vector<int>,greater<int>>minpq;

    minpq.push(10);
    minpq.push(1);
    minpq.push(80);

    priority_queue<int> temp2;
    cout << endl;
    //loop over pq
    while (!minpq.empty()) {
        int x = minpq.top();
        temp2.push(x);
        cout << x << " ";
        minpq.pop();
    }
    //minpq:1 10 80

    //======================================================= 6.set ====================================================
    // #include <set>
    //like priority queue but for unique elements
    //elements are unique and sorted increasingly + has iterator so we can loop on
    //implemented Red black tree

    //6.1 Declaration
    set<int> st;//

    //6.2.a insert
    /*
   -Syntax:pair<iterator,bool> insert (const value_type& val);
   -Extends the container by inserting new elements, effectively increasing the container size by the number of elements
     inserted.
   -Complexity:If a single element is inserted, logarithmic in size in genera
   -return:return a pair, with its member pair::first set to an iterator pointing to either the newly inserted element 
     or to the equivalent element already in the set. The pair::second element in the pair is set to true if a new 
     element was inserted or false if an equivalent element already existed.
   */
    st.insert(10);
    st.insert(1);
    st.insert(10);
    st.insert(50);
    st.insert(-9);
    //st:-9 1 10 50

    //6.2.a insert with hint
    /*
    -Syntax:iterator insert (iterator position, const value_type& val);
   -position parm:Hint for the position where the element can be inserted.
    The function optimizes its insertion time if position points to the element that will precede the inserted element.
    Notice that this is just a hint and does not force the new element to be inserted at that position within the set 
     container (the elements in a set always follow a specific order).
   -Complexity:amortized constant if a hint is given and the position given is the optimal.
   -return:return an iterator pointing to either the newly inserted element or to the element that already had its same 
     value in the set.
   */

   //6.3 looping (it has bidirectional itertator)
    cout<<endl;
    for(auto i:st)
        cout<<i<<" ";
    //-9 1 10 50

    //6.4.a erase
    /*
    -Syntax:size_type erase (const value_type& val);
    -val parm:Value to be removed from the set.
    -Removes from the set container either a single element.
    -Complexity:logarithmic in container size.
    -return: the number of elements erased.
    */
    cout<<st.erase(1); //1(no of removed elements)
    cout<<endl;
    for(auto i:st)
        cout<<i<<" ";
    //-9 10 50

    //6.4.b erase
    /*
    -Syntax:void erase (iterator position);
    -position parm:Iterator pointing to a single element to be removed from the set.
    -Removes from the set container either a single element
    -Complexity:amortized constant.
    -return:none
    */
    st.erase(++st.begin());//10 2nd element
    cout<<endl;
    for(auto i:st)
        cout<<i<<" ";

    //6.4.c erase
    /*
    -Syntax:void erase (iterator first, iterator last);
    -Removes from the set container either a range of elements ([first,last)).
    -Complexity:linear in the distance between first and last..
    -return:none
    */
    st.insert(80);
    //st:-9 50 80
    st.erase(st.begin(),--st.end());//from brgin to last not includong
    cout<<endl;
    for(auto i:st)
        cout<<i<<" ";
    //80


    //6.5 size
    /*same as vector*/
    cout << endl<<st.size() << endl;//1

    //6.6 empty
    /*same as vector*/
    cout << st.empty() << endl;//0

    //6.7 trying to earse not found value => count =0 no exception
    cout<<st.erase(50);//0

    //6.8 Find
    /*
    -Syntax:iterator find (const value_type& val) const;;
    -Searches the container for an element equivalent to val and returns an iterator to it if found, otherwise it 
     returns an iterator to set::end.
    -Complexity:log(n), n is size
    -return:An iterator to the element, if val is found, or set::end otherwise.
    */
    auto it2=st.find(10);
    if(it2==st.end())
        cout<<endl<<"not found"<<endl;
    else cout<<"Found" <<endl;;

    if(it2==st.end())
        cout<<"not found"<<endl;
    else cout<<"Found" <<endl;

    //6.9 set ordered descending
    set<int , greater<>>maxst;
    maxst.insert(1);
    maxst.insert(1);
    maxst.insert(2);
    for(auto i:maxst)
        cout<<i<<" ";
    // 2 1

    //======================================================= 7.Multi set ==============================================
    // #include <set>
    // set + repetition
    //elements are repeated and sorted increasingly + has iterator so we can loop on

    //7.1 Declaration
    multiset<int> multist;//

    //7.2.a b c insert
    /* same as set wth three versions
     * the diffrent may appear in return type due yo diffrent version just chsck when you type
     Note:C++98:There are no guarantees on the relative order of equivalent elements.
        C++11:The relative ordering of equivalent elements is preserved, and newly inserted elements follow their 
        equivalents already in the container.
     */
    multist.insert(10);
    multist.insert(1);
    multist.insert(1);
    multist.insert(1);

    cout<<endl;
    for(auto i:multist)
        cout<<i<<" ";
    //multist:1 1 1 10


    //7.3.a erase
    /*
    -Syntax:size_type erase (const value_type& val);
    -val parm:Value to be removed from the set.
    -Removes from the set container either a single element.
    -Complexity:logarithmic in container size, plus linear in the number of elements removed.
    -return: the number of elements erased.
    */
    cout<<endl;
    cout<<multist.erase(1); //3(no of removed elements)
    cout<<endl;
    for(auto i:st)
        cout<<i<<" ";
    //80

    //6.3 b erase
    multist.insert(1);
    multist.insert(1);
    multist.insert(1);
    multist.insert(2);
    multist.insert(2);
    /*
    -Syntax:iteraor erase (iterator position);
    -position parm:Iterator pointing to a single element to be removed from the set.
    -Removes from the set container either a single element
    -Complexity:amortized constant.
    -return:An iterator pointing to the element immediately following position prior(before) to the element being erased
     . If no such element exists, end() is returned.
    */
    multist.erase(++multist.begin());//1 2nf element
    cout<<endl;
    for(auto i:multist)
        cout<<i<<" ";
    // 1 1  2 2 10
    //Note here remove only 1

    //7.3.c erase
    /*
    -Syntax:iterator erase (iterator first, iterator last);
    -Removes from the set container either a range of elements ([first,last)).
    -Complexity:linear in the distance between first and last..
    -return:The iterator last(the one sent in the function call)
    */
    //multist:1 1 2 2 10
    cout<<endl;
    cout<<*multist.erase(multist.begin(),--multist.end());//from brgin to last not includong //80
    cout<<endl;
    for(auto i:multist)
        cout<<i<<" ";
    //10

    //7.4 size
    /*same as vector*/
    cout << endl<<multist.size() << endl;//1

    //7.5 empty
    /*same as vector*/
    cout << multist.empty() << endl;//0

    //7.6 trying to earse not found value => count =0 no exception
    cout<<multist.erase(50);//0

    //7.7 Count
    /*
    -Syntax:size_type count ( const key_type& k ) const;
    -Searches the container for elements with a value of k and returns the number of elements found.
    -Complexity:Logarithmic in size and linear in the number of matches.
   -return:The number of elements in the container with a key equivalent to k.
   */
    cout<<endl<<multist.count(10)<<endl;//1

    //7.8 Find
    /*Same as set*/

    //7.9 set ordered descending
    multiset<int , greater<>>maxmultist;
    maxmultist.insert(1);
    maxmultist.insert(1);
    maxmultist.insert(2);
    cout<<endl;
    for(auto i:maxmultist)
        cout<<i<<" ";
    // 2 1 1


    //======================================================= 8.unorderedset ===========================================
    // #include <set>
    // set + unordered
    //elements are unique and not sorted + has iterator so we can loop on
    //use hashing

    //8.1 Declaration
    unordered_set<int> unset;//

    //8.2 a b c insert
    /* same as set wth three versions
    /*Complexity:
     Single element insertions:
        Average case: constant.
        Worst case: linear in container size.
    Multiple elements insertion:
        Average case: linear in the number of elements inserted.
        Worst case: N*(size+1): number of elements inserted times the container size plus one.
     */
    unset.insert(10);
    unset.insert(1);
    unset.insert(1);
    unset.insert(1);
    unset.insert(50);
    unset.insert(20);

    cout<<endl;
    for(auto i:unset)
        cout<<i<<" ";
    //unset:20 50 1 10(note no ordering => due to using hashing)

    //8.3.a erase
    /*
    -Syntax:size_type erase ( const key_type& k );;
    -k parm:Value of the element to be erased.Member type key_type is the type of the elements in the container. In 
     unordered_set containers it is the same as value_type,.
    -Removes from the set container either a single element.
    -Complexity:Average:const
                Worst:linear.
    -return: the number of elements erased.
    */
    cout<<endl;
    cout<<unset.erase(10);//1
    cout<<endl;
    for(auto i:unset)
        cout<<i<<" ";
    //20 50 1

    //8.3.b erase
    /*
    -Syntax:iterator erase ( const_iterator position );
    -position parm:Iterator pointing to a single element to be removed from the unordered_set.(Member type 
     const_iterator is a forward iterator type.)
    -Removes from the set container either a single element.
    -Complexity:Average:const
                Worst:linear.
    -return: an iterator pointing to the position immediately following the last of the elements erased.
    */
    cout<<endl<<*unset.erase(unset.begin())<<endl;//50
    for(auto i:unset)
        cout<<i<<" ";
    //50 1

    //8.3.c erase
    /*
    -Syntax:iterator erase ( const_iterator first, const_iterator last );
    -Removes from the unordered_set container either a range of elements ([first,last)).
    -Complexity:Average case: Linear in the number of elements removed.
                Worst case: Linear in the container size.
    -return:an iterator pointing to the position immediately following the last of the elements erased.
    */
    unset.insert(90);
    cout<<endl;
    for(auto i:unset)
        cout<<i<<" ";
    //90 50 1
    unset.erase(unset.begin(),unset.end());
    for(auto i:unset)
        cout<<i<<" ";
    //empty we removed all

    //8.4 find
    /*
    -Syntax:iterator find ( const key_type& k );
            const_iterator find ( const key_type& k ) const;
    -Searches the container for an element with k as value and returns an iterator to it if found, otherwise it returns 
     an iterator to unordered_set::end.
    -Complexity:Average case: constant.
                Worst case: linear in container size.
    -return:An iterator to the element, if the specified value is found, or unordered_set::end if it is not found in the
     container.
    -Note:Member types iterator and const_iterator are forward iterator types. Both may be aliases of the same iterator 
     type.
    */
    if(unset.find(10)==unset.end())
        cout<<endl<<"not found"<<endl;
    else cout<<"Found" <<endl;


    //======================================================= 9.unordered Multi set ====================================
    // #include <set>
    // set + unordered + repeated
    //elements are repeated and not sorted + has iterator so we can loop on
    //use hashing

    //9.1 Declaration
    unordered_multiset<int> unmultiset;//

    //9.2 a insert
    /*
    -Syntax:iterator insert ( const value_type& val );
    -Inserts new element in the unordered_multiset.
    -Complexity:Average case: constant.
                Worst case: linear in container size.
    -return:the function returns an iterator to the newly inserted element.
  */
    unmultiset.insert(1);
    unmultiset.insert(10);
    unmultiset.insert(1);
    unmultiset.insert(2);
    unmultiset.insert(2);
    unmultiset.insert(50);
    cout<<endl;
    for(auto i:unmultiset)
        cout<<i<<" ";
    //unmultiset:50 2 2 10 1 1(note no ordering => due to using hashing)

    //9.2.b insert with hint
    /*
    -Syntax:iterator insert (iterator hint, const value_type& val);
   -hint parm:Hint for the position where the element can be inserted.
    The function optimizes its insertion time if position points to the element that will precede the inserted element.
    Notice that this is just a hint and does not force the new element to be inserted at that position within the set 
     container (the elements in a set always follow a specific order).
   -Complexity:Average case: constant.
               Worst case: linear in container size.
   -return:return an iterator pointing to either the newly inserted element.
   */

    //9.3.a b c erase
    /*Same as unorderd set*/

    //9.4 Count
    /*
    -Syntax:size_type count ( const key_type& k ) const;
    -Searches the container for elements with a value of k and returns the number of elements found.
    -Complexity:Average case: linear in the number of elements counted.
                Worst case: linear in container size.
   -return:The number of elements in the container with a key equivalent to k.
   */
    cout<<endl<<unmultiset.count(1)<<endl;//2

    //9.5 find
    /*Same as unorderd set*/

   //================================================================10.Map=============================================
   //#include <map>
   //Note:keys are sorted ascendingly

   //10.1 Deceleration:
   map<string,int>mp;

   //10.2 []
   /*
    -Syntax:mapped_type& operator[] (const key_type& k);
    -If k matches the key of an element in the container, the function returns a reference to its mapped value.
     If k does not match the key of any element in the container, the function inserts a new element with that key and
     returns a reference to its mapped value. Notice that this always increases the container size by one, even if no
     mapped value is assigned to the element (the element is constructed using its default constructor).
   -return:A reference to the mapped value of the element with a key value equivalent to k.
   -ime complexity: log(n) where n is the size of the map
    */
   mp["Basma"]=10;
   mp["Ypussef"]=20;
   mp["Aya"]=50;

   for(auto i:mp)
       cout<<i.first<<" "<<i.second<<endl;
   //sorted
   //Aya 50
   //Basma 10
   //Ypussef 20

   //10.3 insert
   //insert(pair): This function inserts the pair in the map. The insertion only takes place when the key passed is not
   // already inset.
   //-return:It returns a pointer pair. First element pointing to the pair already present or newly inserted. Second 
   // element returning the boolean status “true” or “false”.
   //Time complexity: log(n) where n is the size of the map
    auto ptr = mp.insert({"string", 20 });

    // checking if the key was already present or newly inserted
    if(ptr.second)
        cout << "The key was newly inserted" ;
    else
        cout << "The key was already present" ;
    cout << endl ;


    mp["a"]=50;
    mp["b"]=50;
    mp["c"]=50;
    mp["d"]=50;

    for(auto i:mp)
        cout<<i.first<<" "<<i.second<<endl;
//    Aya 50
//    Basma 10
//    Ypussef 20
//    a 50
//    b 50
//    c 50
//    d 50

    //10.4.a erase
    /*
     -Syntax:void erase (iterator position);
     -Removes from the map container a single element  pointed to by iterator
     -Return:none
     -Complexity:amortized constant.
    */
    mp.erase(mp.begin());
    for(auto i:mp)
        cout<<i.first<<" "<<i.second<<endl;
//    Basma 10
//    Ypussef 20
//    a 50
//    b 50
//    c 50
//    d 50
//    string 20

    //10.4.b erase
    /*
     -Syntax:size_type erase (const key_type& k);
     -Removes from the map container either a single element with key k
     -Return: the number of elements erased
     -Complexity:logarithmic in container size.
    */
    cout<<mp.erase("a")<<endl;//1
    for(auto i:mp)
        cout<<i.first<<" "<<i.second<<endl;
//    Basma 10
//    Ypussef 20
//    b 50
//    c 50
//    d 50
//    string 20

    //10.4.c erase
    /*
     -Syntax:void erase (iterator first, iterator last);
     -Removes from the map container a range of elements ([first,last)).
     -Return:none
     -Complexity:Linear in the distance between first and last.
    */
    mp.erase(mp.begin(),--mp.end());//[start,lastelemeent(string))
    for(auto i:mp)
        cout<<i.first<<" "<<i.second<<endl;
//    string 20


    //10.5 count
    /*
     -Syntax:size_type count (const key_type& k) const;
     -Count elements with a specific key Because all elements in a map container are unique, the function can only
      return 1 (if the element is found) or zero (otherwise).
     -return:1 if the container contains an element whose key is equivalent to k, or zero otherwise.Member type 
      size_type is an unsigned integral type.
     -Complexity:Logarithmic in size.
     */
    cout<<mp.count("string")<<endl;//1
    cout<<mp.count("Basma")<<endl;//0

    //10.6 find
    /*
     -Synatx:iterator=map_name.find(key) or constant iterator=map_name.find(key)
     -Parameters: The function accepts one mandatory parameter key, which specifies the key to be searched in the map 
     container.
     -Return Value: The function returns an iterator or a constant iterator which refers to the position where the key 
     is present in the map. If the key is not present in the map container, it returns an iterator or a constant 
     iterator which refers to map.end().
     -Complexity:The time complexity for searching elements in std::map is O(log n)
    */
    auto mpit=mp.find("Basma");
    if(mpit!=mp.end())
        cout<<mpit->first<<" "<<mpit->second<<endl;
    else cout<<"not found"<<endl;
    //not found


    //==================================================11.Unordered map==========================================/
    //include<map>
    //map+not ordered

    //11.1 declaration
    unordered_map<string,int>unmp;


    //11.2 []
    /*
    -Syntax:mapped_type& operator[] (const key_type& k);
    -If k matches the key of an element in the container, the function returns a reference to its mapped value.
     If k does not match the key of any element in the container, the function inserts a new element with that key and
     returns a reference to its mapped value. Notice that this always increases the container size by one, even if no
     mapped value is assigned to the element (the element is constructed using its default constructor).
    -return:A reference to the mapped value of the element with a key value equivalent to k.
    -Time complexity: Average case: constant.
Wo                   Worst case: linear in container size.
    */
    unmp["b"]=10;
    unmp["e"]=12;
    unmp["c"]=10;
    unmp["d"]=50;
    unmp["a"]=-9;

    for(auto i:unmp)
        cout<<i.first<<" "<<i.second<<endl;
    //not ordered [Random order]
    //a -9
    //d 50
    //c 10
    //e 12
    //b 10


    //11.3 insert
    /*
    -insert(pair): This function inserts the pair in the map. The insertion only takes place when the key passed is 
     not already inset.
    -return:It returns a pointer pair. First element pointing to the pair already present or newly inserted. Second 
     element returning the boolean status “true” or “false”.
    -Time complexity: Average case: constant.
                       Worst case: linear in container size.
    */
    unmp.insert({"string",10});
    for(auto i:unmp)
        cout<<i.first<<" "<<i.second<<endl;
    //not ordered [Random order]
    //a -9
    //d 50
    //c 10
    //string 10
    //e 12
    //b 10


    //11.4.a erase
    /*
      -Syntax:iterator erase ( const_iterator position );
      -Removes from the unordered_map container a single element
      -Return: an iterator pointing to the position immediately following the last of the elements erased.Member type
      iterator is a forward iterator type.
      -Complexity:Average case: constant
                  Worst case: Linear in the container size.
    */
    unmp.erase(unmp.begin());//a
    for(auto i:unmp)
        cout<<i.first<<" "<<i.second<<endl;
    //d 50
    //c 10
    //string 10
    //e 12
    //b 10


    //11.4.b erase
    /*
      -Syntax:size_type erase ( const key_type& k );
      -Removes from the unordered_map container a single element
      -Return:the number of elements erased.Member type size_type is an unsigned integral type.
      -Complexity:Average case: constant
      Worst case: Linear in the container size.
    */
    unmp.erase("string");
    for(auto i:unmp)
        cout<<i.first<<" "<<i.second<<endl;
    //d 50
    //c 10
    //e 12
    //b 10

    //11.4.c erase
    /*
      -Syntax:iterator erase ( const_iterator first, const_iterator last );
      -Removes from the unordered_map container either a range of elements ([first,last)).
      -Return: an iterator pointing to the position immediately following the last of the elements erased.Member type
      iterator is a forward iterator type.
      -Complexity:Average case: Linear in the number of elements removed.
                  Worst case: Linear in the container size.
    */
    unmp.erase(unmp.begin(),unmp.end());
    for(auto i:unmp)
        cout<<i.first<<" "<<i.second<<endl;
    //empty

    //11.5 count
    /*
     -Syntax:size_type count (const key_type& k) const;
     -Count elements with a specific key Because all elements in a map container are unique, the function can only
      return 1 (if the element is found) or zero (otherwise).
     -return:1 if the container contains an element whose key is equivalent to k, or zero otherwise.Member type 
     size_type is an unsigned integral type.
     -Complexity:Average case: linear in the number of elements counted.
                 Worst case: linear in container size.
     */
    cout<<mp.count("string")<<endl;//0
    cout<<mp.count("b")<<endl;//1


    //11.6 find
  /*
   -find function in C++ is used to search for a specific key in an unordered map.
   -Syntax:iterator find ( const key_type& k );const_iterator find ( const key_type& k ) const;
   -Parameters: It takes the key as a parameter.
   -Return values: If the given key exists in unordered_map it returns an iterator to that element otherwise it returns
   the end of the map iterator.Member types iterator and const_iterator are forward iterator types.
   -Time Complexity : Average case: constant.
                      Worst case: linear in container size.
  */
  unmp["b"]=50;
  auto itmap= unmp.find("b");
  if(itmap==unmp.end())
      cout<<"not found"<<endl;
  else cout<<"Found"<<itmap->first<<" "<<itmap->second<<endl;




    //==================================================12.Multi map==========================================/
    //include<map>
    //map=ordered + duplictes in eky
    //12.1 Decleration:
    multimap<string,int>mltimp;

    //12.2 []  NOT HERE:)  due to having duplicate keys
    //mltimp["ali"]=12; //ERROR

    //12.3 insert
    /*
     -Syntax:iterator insert (const value_type& val);
     -val parm :defined in multimap as pair<const key_type,mapped_type>
     -Extends the container by inserting new elements, effectively increasing the container size by the number of
     elements inserted.
      Internally, multimap containers keep all their elements sorted by key following the criterion specified by its
      comparison object.
      The elements are always inserted in its respective position following this ordering.
     Note:There are no guarantees on the relative order of equivalent elements.
     -Return:iterator pointing to the newly inserted element in the multiset.Member type iterator is a bidirectional
     iterator type that points to elements.
     -Complexity:logarithmic in size
     */
    mltimp.insert({"A",10});
    mltimp.insert({"B",20});
    mltimp.insert({"D",-9});
    mltimp.insert({"C",30});
    mltimp.insert({"C",80});
    mltimp.insert({"C",500});
    mltimp.insert({"C",-7});



    for(auto i:mltimp)
        cout<<i.first<<" "<<i.second<<endl;
    //A 10
    //B 20
    //C 30
    //C 80
    //C 500
    //C -7
    //D -9



    //12.4.a erase
    /*
      -Syntax: void erase (iterator position);
      -Member types iterator and const_iterator are bidirectional iterator types that point to elements.
      -Removes elements from the multimap container
      -Return:none
      -Complexity:amortized constant.
    */
    mltimp.erase(mltimp.begin());
    for(auto i:mltimp)
        cout<<i.first<<" "<<i.second<<endl;
    //B 20
    //C 30
    //C 80
    //C 500
    //C -7
    //D -9


    //12.4.b erase
    /*
      -Syntax:size_type erase (const key_type& k);
      -Member types iterator and const_iterator are bidirectional iterator types that point to elements.
      -Removes elements from the multimap container
      -Return: returns the number of elements erased.Member type size_type is an unsigned integral type.
      -Complexity:logarithmic in container size, plus linear in the number of elements removed.
    */
    cout<<mltimp.erase("C")<<endl;//4
    for(auto i:mltimp)
        cout<<i.first<<" "<<i.second<<endl;
    //B 20
    //D -9

    //12.4.c erase
    /*
      -Syntax:void erase (iterator first, iterator last);
      -Removes elements from the multimap container
      -Return:none
      -Complexity: linear in the distance between first and last.
    */
    mltimp.erase(mltimp.begin(),--mltimp.end());//B
    for(auto i:mltimp)
        cout<<i.first<<" "<<i.second<<endl;
    //D -9

    //12.5 count
    /*
    -Syntax:size_type count (const key_type& k) const;
    -Searches the container for elements with a key equivalent to k and returns the number of matches.
     Two keys are considered equivalent if the container's comparison object returns false reflexively (i.e., no matter
     the order in which the keys are passed as arguments).rn:
    -return:The number of elements in the container contains that have a key equivalent to k.Member type size_type is 
     an unsigned integral type.
    -complexity:Logarithmic in size, plus linear in the number of matches.
    */
    mltimp.insert({"D",8});
    cout<<mltimp.count("D")<<endl;//2
//    D -9
//    D 8

    //12.3 find
    /*
     -Syntax:iterator find (const key_type& k);const_iterator find (const key_type& k) const;
     -Searches the container for an element with a key equivalent to k and returns an iterator to it if found, 
     otherwise it returns an iterator to multimap::end.
     NOTE***:Notice that this function returns an iterator to a single element (of the possibly multiple elements with
     equivalent keys). To obtain the entire range of equivalent elements, see multimap::equal_range.
     -return:An iterator to the element, if an element with specified key is found, or multimap::end otherwise.Member
     types iterator and const_iterator are bidirectional iterator types pointing to elements (of type value_type).
     -Complexity:Logarithmic in size.
    */

    auto itmmp=mltimp.find("D");
    if(itmmp!=mltimp.end())
        cout<<"Found "<<itmmp->first<<" "<<itmmp->second<<endl;
    else cout<<"Not found"<<endl;


    //==================================================13.unordered Multi map=========================================/
    //include<map>
    //map+unordered + duplictes in key
    //13.1 Decleration:
    unordered_multimap<string,int>unmmp;


    //13.2 []  NOT HERE:)  due to having duplicate keys
    //mltimp["ali"]=12; //ERROR

    //13.3insert
    /*
     -Syntax:iterator insert (const value_type& val);
     -val parm :defined in multimap as pair<const key_type,mapped_type>
     -Return:iterator pointing to the newly inserted element in the multiset.Member type iterator is a forward 
     iterator type.
     -Complexity:Average case: constant.
                Worst case: linear in container size.
     */
    unmmp.insert({"A",10});
    unmmp.insert({"B",20});
    unmmp.insert({"D",-9});
    unmmp.insert({"C",30});
    unmmp.insert({"C",80});
    unmmp.insert({"C",500});
    unmmp.insert({"C",-7});

    for(auto i:unmmp)
        cout<<i.first<<" "<<i.second<<endl;
//    B 20
//    C -7
//    C 500
//    C 80
//    C 30
//    D -9
//    A 10

    //13.4.a erase
    /*
      -Syntax:iterator erase ( const_iterator position );
      -Removes a single element to be removed from the unordered_multimap
      -Return:an iterator pointing to the position immediately following the last of the elements erased.Member type
      iterator is a forward iterator type.
      -Complexity:constant
                  Worst case: Linear in the container size.
    */
    unmmp.erase(unmmp.begin());//B
    for(auto i:unmmp)
        cout<<i.first<<" "<<i.second<<endl;
//    C -7
//    C 500
//    C 80
//    C 30
//    D -9
//    A 10

    //13.4.b erase
    /*
      -Syntax:size_type erase ( const key_type& k );
      -Removes from the unordered_multimap container the elements whose key is k
      -Return:returns the number of elements erased.Member type size_type is an unsigned integral type.

      -Complexity:constant
                  Worst case: Linear in the container size.
    */
    cout<<unmmp.erase("C")<<endl;//4
    for(auto i:unmmp)
        cout<<i.first<<" "<<i.second<<endl;
//    D -9
//    A 10

    //13.4.c erase
    /*
      -Syntax:iterator erase ( const_iterator first, const_iterator last );
      -Removes from the unordered_multimap container either the elements those in a range ([first,last)).
      -Return:an iterator pointing to the position immediately following the last of the elements erased.Member type
      iterator is a forward iterator type.
      -Complexity:Average case: Linear in the number of elements removed.
                  Worst case: Linear in the container size.
    */
    unmmp.erase(unmmp.begin(),unmmp.end());
    for(auto i:unmmp)
        cout<<i.first<<" "<<i.second<<endl;
//   empty


    //13.5 count
    /*
     -Syntax:size_type count ( const key_type& k ) const;
     -Count elements with a specific key.Searches the container for elements whose key is k and returns the number of
     elements found.
     -return:The number of elements in the container with a key equivalent to k.Member type size_type is an unsigned
     integral type.
     -complexity:Average case: linear in the number of elements counted.
                 Worst case: linear in container size.
     */
    unmmp.insert({"C",30});
    unmmp.insert({"C",80});
    unmmp.insert({"C",500});
    unmmp.insert({"C",-7});

    cout<<unmmp.count("C")<<endl;//4

    //13.6 Find
    /*
    -Syntax:iterator find ( const key_type& k );const_iterator find ( const key_type& k ) const;
    -Searches the container for an element with k as key and returns an iterator to it if found, otherwise it returns
     an iterator to unordered_multimap::end (the element past the end of the container).
     To obtain a range with all the elements whose key is k you can use member function equal_range.
     To just check whether a particular key exists, you can use count.
     -return:An iterator to the element, if the specified key value is found, or unordered_multimap::end if the
     specified key is not found in the container.Member types iterator and const_iterator are forward iterator types.
    -Complexity:Average case: constant.
                Worst case: linear in container size.
    */

    auto itunmmp=unmmp.find("C");
    if(itunmmp!=unmmp.end())
        cout<<"Found "<<itunmmp->first<<" "<<itunmmp->second<<endl;
    else cout<<"Not found"<<endl;

    //====================================Sort & Reverse functions =====================================================
    //For types of iterators refer to word notes
    // 1.sort
    // Syntax:void sort (RandomAccessIterator first, RandomAccessIterator last);
    // #include <algorithm>
    /*-Sorts the elements in the range [first,last) into ascending order.
    -****Equivalent elements are not guaranteed to keep their original relative order (unstable order)
    -Complexity:O(Nlog(N))
    -return:none
    */
    cout << endl;
    vector<int> vec = {5, 8, 1, 9, 0, 4};
    sort(vec.begin(), vec.end());
    for (auto i : vec)
        cout << i << " "; // 0 1 4 5 8 9

        cout<<endl;

     //if you want to sort descending
     vec= {5, 8, 1, 9, 0, 4};
    sort(vec.rbegin(),vec.rend()); //9 8 5 4 1 0
    for(auto i:vec)
        cout<<i<<" ";

    // 2.Reverse
    // Syntax:void reverse(BidirectionalIterator first, BidirectionalIterator last)
    // #include <algorithm>
    /*
    - It reverses the order of the elements in the range [first, last) of any container.
    -Complexity: O(n).
    -return:none
    */
    cout << endl;
    vec = {5, 8, 1, 9, 0, 4};
    reverse(vec.begin(), vec.end());
    for (auto i : vec)
        cout << i << " "; // 4 0 9 1 8 5
}
```
