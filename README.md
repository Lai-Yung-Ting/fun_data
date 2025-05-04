import React, { useState } from 'react';

function CreateTask() {
  const [title, setTitle] = useState('');
  const [description, setDescription] = useState('');
  const [budget, setBudget] = useState(0);
  const [deadline, setDeadline] = useState(''); // 新增狀態

  const handleSubmit = () => {
    // 處理任務發布邏輯，例如將任務資料傳送到後端
    console.log('Task submitted:', { title, description, budget, deadline });
    alert('Task submitted! (This is a simulation)');
    
    // 清空表單以便用戶可以輸入新的任務
    setTitle('');
    setDescription('');
    setBudget(0);
    setDeadline(''); // 清空截止日期
  };

  return (
    <div>
      <h2>發布新任務</h2>
      <div>
        <label>標題：</label>
        <input
          type="text"
          value={title}
          onChange={(e) => setTitle(e.target.value)}
        />
      </div>
      <div>
        <label>描述：</label>
        <textarea
          value={description}
          onChange={(e) => setDescription(e.target.value)}
        />
      </div>
      <div>
        <label>預算 (USD)：</label>
        <input
          type="number"
          value={budget}
          onChange={(e) => setBudget(Number(e.target.value))}
        />
      </div>
      <div>
        <label>截止日期：</label> {/* 新增欄位 */}
        <input
          type="date"
          value={deadline}
          onChange={(e) => setDeadline(e.target.value)}
        />
      </div>
      <button onClick={handleSubmit}>發布任務</button>
    </div>
  );
}
