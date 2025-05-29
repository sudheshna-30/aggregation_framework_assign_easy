<pre># aggregation_framework_assign_easy



use aggregationAssignmentDB
switched to db aggregationAssignmentDB
db.products.insertMany([
  { name: "Laptop Pro", category: "Electronics", price: 1200, quantity: 10, tags: ["computer", "portable", "work"], date_added: new Date("2023-01-15T10:00:00Z"), supplier: { name: "TechGlobe", location: "USA" } },
  { name: "Wireless Mouse", category: "Electronics", price: 25, quantity: 100, tags: ["peripheral", "computer", "wireless"], date_added: new Date("2023-02-01T11:30:00Z"), supplier: { name: "GadgetPro", location: "China" } },
  { name: "Mechanical Keyboard", category: "Electronics", price: 75, quantity: 50, tags: ["peripheral", "computer", "mechanical"], date_added: new Date("2023-01-20T14:00:00Z"), supplier: { name: "TechGlobe", location: "USA" } },
  { name: "Cotton T-Shirt", category: "Apparel", price: 20, quantity: 200, tags: ["clothing", "cotton", "casual"], date_added: new Date("2023-03-10T09:00:00Z"), supplier: { name: "FashionHub", location: "India" } },
  { name: "Denim Jeans", category: "Apparel", price: 60, quantity: 80, tags: ["clothing", "denim"], date_added: new Date("2023-03-01T16:45:00Z"), supplier: { name: "FashionHub", location: "India" } },
  { name: "Espresso Machine", category: "Home Goods", price: 250, quantity: 30, tags: ["kitchen", "appliance", "coffee"], date_added: new Date("2023-02-15T08:20:00Z"), supplier: { name: "HomeBest", location: "Germany" } },
  { name: "Smartwatch", category: "Electronics", price: 199, quantity: 25, tags: ["wearable", "gadget", "portable"], date_added: new Date("2023-04-01T12:00:00Z"), supplier: { name: "GadgetPro", location: "China" } },
  { name: "Leather Wallet", category: "Accessories", price: 45, quantity: 120, tags: ["fashion", "leather"], date_added: new Date("2023-03-20T10:10:00Z"), supplier: { name: "StyleCraft", location: "Italy" } },
  { name: "Yoga Mat", category: "Sports", price: 30, quantity: 90, tags: ["fitness", "exercise"], date_added: new Date("2023-04-05T13:00:00Z"), supplier: { name: "ActiveLife", location: "USA" } },
  { name: "Bluetooth Speaker", category: "Electronics", price: 80, quantity: 60, tags: ["audio", "portable", "wireless"], date_added: new Date("2023-02-25T17:00:00Z"), supplier: { name: "SoundWave", location: "USA" } }
]);
{
  acknowledged: true,
  insertedIds: {
    '0': ObjectId('683839af09e21a79c8e563a5'),
    '1': ObjectId('683839af09e21a79c8e563a6'),
    '2': ObjectId('683839af09e21a79c8e563a7'),
    '3': ObjectId('683839af09e21a79c8e563a8'),
    '4': ObjectId('683839af09e21a79c8e563a9'),
    '5': ObjectId('683839af09e21a79c8e563aa'),
    '6': ObjectId('683839af09e21a79c8e563ab'),
    '7': ObjectId('683839af09e21a79c8e563ac'),
    '8': ObjectId('683839af09e21a79c8e563ad'),
    '9': ObjectId('683839af09e21a79c8e563ae')
  }
}
db.products.aggregate({})
MongoServerError[Location40323]: A pipeline stage specification object must contain exactly one field.
db.products.aggregate([
  {$match:{
		category: "Electronics"
}
}
])
{
  _id: ObjectId('683839af09e21a79c8e563a5'),
  name: 'Laptop Pro',
  category: 'Electronics',
  price: 1200,
  quantity: 10,
  tags: [
    'computer',
    'portable',
    'work'
  ],
  date_added: 2023-01-15T10:00:00.000Z,
  supplier: {
    name: 'TechGlobe',
    location: 'USA'
  }
}
{
  _id: ObjectId('683839af09e21a79c8e563a6'),
  name: 'Wireless Mouse',
  category: 'Electronics',
  price: 25,
  quantity: 100,
  tags: [
    'peripheral',
    'computer',
    'wireless'
  ],
  date_added: 2023-02-01T11:30:00.000Z,
  supplier: {
    name: 'GadgetPro',
    location: 'China'
  }
}
{
  _id: ObjectId('683839af09e21a79c8e563a7'),
  name: 'Mechanical Keyboard',
  category: 'Electronics',
  price: 75,
  quantity: 50,
  tags: [
    'peripheral',
    'computer',
    'mechanical'
  ],
  date_added: 2023-01-20T14:00:00.000Z,
  supplier: {
    name: 'TechGlobe',
    location: 'USA'
  }
}
{
  _id: ObjectId('683839af09e21a79c8e563ab'),
  name: 'Smartwatch',
  category: 'Electronics',
  price: 199,
  quantity: 25,
  tags: [
    'wearable',
    'gadget',
    'portable'
  ],
  date_added: 2023-04-01T12:00:00.000Z,
  supplier: {
    name: 'GadgetPro',
    location: 'China'
  }
}
{
  _id: ObjectId('683839af09e21a79c8e563ae'),
  name: 'Bluetooth Speaker',
  category: 'Electronics',
  price: 80,
  quantity: 60,
  tags: [
    'audio',
    'portable',
    'wireless'
  ],
  date_added: 2023-02-25T17:00:00.000Z,
  supplier: {
    name: 'SoundWave',
    location: 'USA'
  }
}
db.products.aggregate([
  {
		$group : {
				_id: "$category",
				count : {$sum : 1}
}
}
])

<img width="191" alt="image" src="https://github.com/user-attachments/assets/ba0bbe72-3475-474a-8d24-58f2452d65c8" />

{
  _id: 'Apparel',
  count: 2
}
{
  _id: 'Home Goods',
  count: 1
}
{
  _id: 'Electronics',
  count: 5
}
{
  _id: 'Accessories',
  count: 1
}
{
  _id: 'Sports',
  count: 1
}
db.products.aggregate([
  {
		$project : {
			_id:0,
			name : 1,
			price : 1
}
},
  {
    $sort:{
    price:1
}
}
])

<img width="209" alt="image" src="https://github.com/user-attachments/assets/6c790a49-2620-4f3d-a915-362b131fd970" />
<img width="211" alt="image" src="https://github.com/user-attachments/assets/09d5f43c-763f-44c0-9ced-9f37ed5818bd" />

{
  name: 'Cotton T-Shirt',
  price: 20
}
{
  name: 'Wireless Mouse',
  price: 25
}
{
  name: 'Yoga Mat',
  price: 30
}
{
  name: 'Leather Wallet',
  price: 45
}
{
  name: 'Denim Jeans',
  price: 60
}
{
  name: 'Mechanical Keyboard',
  price: 75
}
{
  name: 'Bluetooth Speaker',
  price: 80
}
{
  name: 'Smartwatch',
  price: 199
}
{
  name: 'Espresso Machine',
  price: 250
}
{
  name: 'Laptop Pro',
  price: 1200
}

</pre>
