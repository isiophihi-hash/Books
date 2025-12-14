# Books
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>100 Books Collection</title>
<style>
    body { font-family: Arial, sans-serif; background-color: #f2f2f2; margin:0; padding:0; }
    header { background-color: #e74c3c; color: white; padding: 20px; text-align: center; }
    .book-list { display: flex; flex-wrap: wrap; justify-content: center; margin: 20px; }
    .book { background-color: white; border: 1px solid #ccc; border-radius: 8px; margin: 10px; padding: 15px; width: 200px; text-align: center; }
    .book img { max-width: 100%; height: auto; }
    .book h3 { margin: 10px 0 5px 0; }
    .book p { color: #555; font-size: 14px; }
</style>
</head>
<body>
<header>
    <h1>100 Books Collection</h1>
</header>
<div class="book-list" id="book-list"></div>

<script>
    const books = [
        { title: "To Kill a Mockingbird", author: "Harper Lee", image: "https://via.placeholder.com/150" },
        { title: "1984", author: "George Orwell", image: "https://via.placeholder.com/150" },
        { title: "Pride and Prejudice", author: "Jane Austen", image: "https://via.placeholder.com/150" },
        { title: "The Great Gatsby", author: "F. Scott Fitzgerald", image: "https://via.placeholder.com/150" },
        { title: "Moby Dick", author: "Herman Melville", image: "https://via.placeholder.com/150" },
        { title: "War and Peace", author: "Leo Tolstoy", image: "https://via.placeholder.com/150" },
        { title: "Crime and Punishment", author: "Fyodor Dostoevsky", image: "https://via.placeholder.com/150" },
        { title: "The Catcher in the Rye", author: "J.D. Salinger", image: "https://via.placeholder.com/150" },
        { title: "Brave New World", author: "Aldous Huxley", image: "https://via.placeholder.com/150" },
        { title: "Jane Eyre", author: "Charlotte Brontë", image: "https://via.placeholder.com/150" },
        { title: "Wuthering Heights", author: "Emily Brontë", image: "https://via.placeholder.com/150" },
        { title: "The Odyssey", author: "Homer", image: "https://via.placeholder.com/150" },
        { title: "The Iliad", author: "Homer", image: "https://via.placeholder.com/150" },
        { title: "Frankenstein", author: "Mary Shelley", image: "https://via.placeholder.com/150" },
        { title: "Dracula", author: "Bram Stoker", image: "https://via.placeholder.com/150" },
        { title: "Les Misérables", author: "Victor Hugo", image: "https://via.placeholder.com/150" },
        { title: "The Count of Monte Cristo", author: "Alexandre Dumas", image: "https://via.placeholder.com/150" },
        { title: "Don Quixote", author: "Miguel de Cervantes", image: "https://via.placeholder.com/150" },
        { title: "The Brothers Karamazov", author: "Fyodor Dostoevsky", image: "https://via.placeholder.com/150" },
        { title: "Anna Karenina", author: "Leo Tolstoy", image: "https://via.placeholder.com/150" },
        { title: "The Hobbit", author: "J.R.R. Tolkien", image: "https://via.placeholder.com/150" },
        { title: "The Lord of the Rings", author: "J.R.R. Tolkien", image: "https://via.placeholder.com/150" },
        { title: "Harry Potter and the Sorcerer's Stone", author: "J.K. Rowling", image: "https://via.placeholder.com/150" },
        { title: "Harry Potter and the Chamber of Secrets", author: "J.K. Rowling", image: "https://via.placeholder.com/150" },
        { title: "Harry Potter and the Prisoner of Azkaban", author: "J.K. Rowling", image: "https://via.placeholder.com/150" },
        { title: "Harry Potter and the Goblet of Fire", author: "J.K. Rowling", image: "https://via.placeholder.com/150" },
        { title: "Harry Potter and the Order of the Phoenix", author: "J.K. Rowling", image: "https://via.placeholder.com/150" },
        { title: "Harry Potter and the Half-Blood Prince", author: "J.K. Rowling", image: "https://via.placeholder.com/150" },
        { title: "Harry Potter and the Deathly Hallows", author: "J.K. Rowling", image: "https://via.placeholder.com/150" },
        { title: "The Chronicles of Narnia: The Lion, the Witch and the Wardrobe", author: "C.S. Lewis", image: "https://via.placeholder.com/150" },
        { title: "The Chronicles of Narnia: Prince Caspian", author: "C.S. Lewis", image: "https://via.placeholder.com/150" },
        { title: "The Chronicles of Narnia: The Voyage of the Dawn Treader", author: "C.S. Lewis", image: "https://via.placeholder.com/150" },
        { title: "The Chronicles of Narnia: The Silver Chair", author: "C.S. Lewis", image: "https://via.placeholder.com/150" },
        { title: "The Chronicles of Narnia: The Horse and His Boy", author: "C.S. Lewis", image: "https://via.placeholder.com/150" },
        { title: "The Chronicles of Narnia: The Magician's Nephew", author: "C.S. Lewis", image: "https://via.placeholder.com/150" },
        { title: "The Chronicles of Narnia: The Last Battle", author: "C.S. Lewis", image: "https://via.placeholder.com/150" },
        { title: "Alice's Adventures in Wonderland", author: "Lewis Carroll", image: "https://via.placeholder.com/150" },
        { title: "Through the Looking-Glass", author: "Lewis Carroll", image: "https://via.placeholder.com/150" },
        { title: "The Little Prince", author: "Antoine de Saint-Exupéry", image: "https://via.placeholder.com/150" },
        { title: "The Alchemist", author: "Paulo Coelho", image: "https://via.placeholder.com/150" },
        { title: "The Da Vinci Code", author: "Dan Brown", image: "https://via.placeholder.com/150" },
        { title: "Angels & Demons", author: "Dan Brown", image: "https://via.placeholder.com/150" },
        { title: "Inferno", author: "Dan Brown", image: "https://via.placeholder.com/150" },
        { title: "Origin", author: "Dan Brown", image: "https://via.placeholder.com/150" },
        { title: "Digital Fortress", author: "Dan Brown", image: "https://via.placeholder.com/150" },
        { title: "The Hunger Games", author: "Suzanne Collins", image: "https://via.placeholder.com/150" },
        { title: "Catching Fire", author: "Suzanne Collins", image: "https://via.placeholder.com/150" },
        { title: "Mockingjay", author: "Suzanne Collins", image: "https://via.placeholder.com/150" },
        { title: "Divergent", author: "Veronica Roth", image: "https://via.placeholder.com/150" },
        { title: "Insurgent", author: "Veronica Roth", image: "https://via.placeholder.com/150" },
        { title: "Allegiant", author: "Veronica Roth", image: "https://via.placeholder.com/150" },
        { title: "Twilight", author: "Stephenie Meyer", image: "https://via.placeholder.com/150" },
        { title: "New Moon", author: "Stephenie Meyer", image: "https://via.placeholder.com/150" },
        { title: "Eclipse", author: "Stephenie Meyer", image: "https://via.placeholder.com/150" },
        { title: "Breaking Dawn", author: "Stephenie Meyer", image: "https://via.placeholder.com/150" },
        { title: "The Shining", author: "Stephen King", image: "https://via.placeholder.com/150" },
        { title: "It", author: "Stephen King", image: "https://via.placeholder.com/150" },
        { title: "Carrie", author: "Stephen King", image: "https://via.placeholder.com/150" },
        { title: "Misery", author: "Stephen King", image: "https://via.placeholder.com/150" },
        { title: "Pet Sematary", author: "Stephen King", image: "https://via.placeholder.com/150" },
        { title: "Doctor Sleep", author: "Stephen King", image: "https://via.placeholder.com/150" },
        { title: "The Stand", author: "Stephen King", image: "https://via.placeholder.com/150" },
        { title: "The Outsider", author: "Stephen King", image: "https://via.placeholder.com/150" },
        { title: "It Ends with Us", author: "Colleen Hoover", image: "https://via.placeholder.com/150" },
        { title: "Verity", author: "Colleen Hoover", image: "https://via.placeholder.com/150" },
        { title: "Reminders of Him", author: "Colleen Hoover", image: "https://via.placeholder.com/150" },
        { title: "Ugly Love", author: "Colleen Hoover", image: "https://via.placeholder.com/150" },
        { title: "November 9", author: "Colleen Hoover", image: "https://via.placeholder.com/150" },
        { title: "Confess", author: "Colleen Hoover", image: "https://via.placeholder.com/150" },
        { title: "Slammed", author: "Colleen Hoover", image: "https://via.placeholder.com/150" },
        { title: "Hopeless", author: "Colleen Hoover", image: "https://via.placeholder.com/150" },
        { title: "Point of Retreat", author: "Colleen Hoover", image: "https://via.placeholder.com/150" },
        { title: "Finding Cinderella", author: "Colleen Hoover", image: "https://via.placeholder.com/150" },
        { title: "The Fault in Our Stars", author: "John Green", image: "https://via.placeholder.com/150" },
        { title: "Looking for Alaska", author: "John Green", image: "https://via.placeholder.com/150" },
        { title: "Paper Towns", author: "John Green", image: "https://via.placeholder.com/150" },
        { title: "Turtles All the Way Down", author: "John Green", image: "https://via.placeholder.com/150" },
        { title: "An Abundance of Katherines", author: "John Green", image: "https://via.placeholder.com/150" },
        { title: "Will Grayson, Will Grayson", author: "John Green & David Levithan", image: "https://via.placeholder.com/150" },
        { title: "Looking for Alaska", author: "John Green", image: "https://via.placeholder.com/150" },
        { title: "Fangirl", author: "Rainbow Rowell", image: "https://via.placeholder.com/150" },
        { title: "Eleanor & Park", author: "Rainbow Rowell", image: "https://via.placeholder.com/150" },
        { title: "Carry On", author: "Rainbow Rowell", image: "https://via.placeholder.com/150" },
        { title: "Landline", author: "Rainbow Rowell", image: "https://via.placeholder.com/150" },
        { title: "Attachments", author: "Rainbow Rowell", image: "https://via.placeholder.com/150" },
        { title: "Simon vs. the Homo Sapiens Agenda", author: "Becky Albertalli", image: "https://via.placeholder.com/150" },
        { title: "Leah on the Offbeat", author: "Becky Albertalli", image: "https://via.placeholder.com/150" },
        { title: "The Upside of Unrequited", author: "Becky Albertalli", image: "https://via.placeholder.com/150" },
        { title: "Love, Creekwood", author: "Becky Albertalli", image: "https://via.placeholder.com/150" },
        { title: "What If It's Us", author: "Adam Silvera & Becky Albertalli", image: "https://via.placeholder.com/150" },
        { title: "They Both Die at the End", author: "Adam Silvera", image: "https://via.placeholder.com/150" },
        { title: "History Is All You Left Me", author: "Adam Silvera", image: "https://via.placeholder.com/150" },
        { title: "More Happy Than Not", author: "Adam Silvera", image: "https://via.placeholder.com/150" },
        { title: "Infinity Son", author: "Adam Silvera", image: "https://via.placeholder.com/150" },
        { title: "Infinity Reaper", author: "Adam Silvera", image: "https://via.placeholder.com/150" },
        { title: "Infinity Kings", author: "Adam Silvera", image: "https://via.placeholder.com/150" }
    ];

    const bookList = document.getElementById('book-list');
    books.forEach(book => {
        const bookDiv = document.createElement('div');
        bookDiv.classList.add('book');
        bookDiv.innerHTML = `
            <img src="${book.image}" alt="${book.title}">
            <h3>${book.title}</h3>
            <p>${book.author}</p>
        `;
        bookList.appendChild(bookDiv);
    });
</script>
</body>
</html>
