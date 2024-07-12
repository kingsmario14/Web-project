import React, {useState} from 'react';
const App = () => {
  let [val, setVal] = useState("");
  let [nums, setNums] = useState([6, 8, 9, 10, 16, 18, 8]);
  const addNum=()=>{
    setNums([...nums, val]);
  }
  const deleteNum=ind=>{
    let result = nums.filter((val, myIndex)=>myIndex===ind);
    setNums(result)
  }
  return (
    <div>
      <input onChange = {e=>setVal(e.target.value)}/>
      <button onClick={addNum}>add number</button>
      {nums.length > 0? nums.map((val, i)=>(

        <div key={i}>I have {val} phones
        <button onClick={()=>deleteNum(i)}>delete</button>
      </div>

      ))
      :
      <div>No value yet</div>
    }
    </div>
)}
export default App;
