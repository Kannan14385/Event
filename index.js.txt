const express = require('express');
const app = express();
const PORT = process.env.PORT || 3000;

app.use(express.static('public'));
app.use(express.urlencoded({ extended: true }));

app.get('/', (req, res) => {
  res.sendFile(__dirname + '/public/index.html');
});

app.post('/register', (req, res) => {
  console.log('Registration Data:', req.body);
  res.send('Thank you for registering!');
});

app.listen(PORT, () => {
  console.log(`Server running on port ${PORT}`);
});
