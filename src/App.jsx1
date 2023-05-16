import { useEffect, useState } from 'react';

const App = () => {
  const [audits, setAudits] = useState([]);

  useEffect(() => {
    const fetchData = async () => {
      try {
        const response = await fetch('https://api.safetyculture.io/audits/search', {
          headers: {
            'Authorization': 'Bearer ce5eceab4cad6be0c4a3bafdf0ee3a98b710baa4a40a97502423e0b25de732bc'
          }
        });
        const data = await response.json();
        setAudits(data);
      } catch (error) {
        console.error(error);
      }
    };

    fetchData();
  }, []);

  return (
    <div>
      <h1>Audits</h1>
      {audits.map(audit => (
        <div key={audit.id}>
          <h2>{audit.title}</h2>
          <p>Created By: {audit.createdBy}</p>
        </div>
      ))}
    </div>
  );
};

export default App;
