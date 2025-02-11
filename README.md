<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Legal Services Platform</title>
    <style>
        body { font-family: Arial, sans-serif; margin: 0; padding: 0; background-color: #f4f4f4; }
        header { background: #333; color: #fff; padding: 15px; text-align: center; }
        nav { text-align: center; padding: 10px; background: #444; }
        nav a { color: #fff; text-decoration: none; padding: 10px 20px; }
        section { padding: 20px; }
        .service { background: #fff; padding: 20px; margin: 20px; border-radius: 5px; box-shadow: 0 0 10px rgba(0,0,0,0.1); }
        .service h2 { color: #333; }
        .categories { display: flex; flex-wrap: wrap; gap: 20px; justify-content: center; }
        .category { background: #fff; padding: 20px; border-radius: 5px; box-shadow: 0 0 10px rgba(0,0,0,0.1); width: 200px; text-align: center; cursor: pointer; }
        .lawyer-profile { display: none; flex-wrap: wrap; gap: 20px; }
        .lawyer { background: #fff; padding: 20px; border-radius: 5px; box-shadow: 0 0 10px rgba(0,0,0,0.1); width: 300px; text-align: center; }
        .lawyer img { width: 100px; height: 100px; border-radius: 50%; }
    </style>
    <script>
        function showLawyers(category) {
            document.querySelectorAll('.lawyer-profile').forEach(profile => {
                profile.style.display = 'none';
            });
            document.getElementById(category).style.display = 'flex';
        }
        function updatePicture(event, lawyerId) {
            const file = event.target.files[0];
            if (file) {
                const reader = new FileReader();
                reader.onload = function(e) {
                    document.getElementById(lawyerId).src = e.target.result;
                };
                reader.readAsDataURL(file);
            }
        }
    </script>
</head>
<body>
    <header>
        <h1>Legal Services Platform</h1>
    </header>
    <nav>
        <a href="#consultation">Lawyer Consultation</a>
        <a href="#contracts">Legal Contracts</a>
        <a href="#licensing">Business Licensing</a>
        <a href="#lawyers">Lawyers</a>
        <a href="#contact">Contact Us</a>
        <a href="#edit">Edit</a>
    </nav>
    <section id="lawyers" class="service">
        <h2>Legal Specialties</h2>
        <div class="categories">
            <div class="category" onclick="showLawyers('corporate')">Corporate Law</div>
            <div class="category" onclick="showLawyers('family')">Family Law</div>
            <div class="category" onclick="showLawyers('criminal')">Criminal Law</div>
        </div>
        <div id="corporate" class="lawyer-profile">
            <div class="lawyer">
                <img id="lawyer1" src="uploaded_lawyer_image.jpg" alt="Lawyer 1">
                <h3>John Doe</h3>
                <p>Degree: LLB, Harvard Law School</p>
                <p>Specialty: Corporate Law</p>
                <p>Rating: ★★★★☆</p>
                <input type="file" onchange="updatePicture(event, 'lawyer1')">
            </div>
        </div>
        <div id="family" class="lawyer-profile">
            <div class="lawyer">
                <img id="lawyer2" src="uploaded_lawyer_image.jpg" alt="Lawyer 2">
                <h3>Jane Smith</h3>
                <p>Degree: JD, Yale Law School</p>
                <p>Specialty: Family Law</p>
                <p>Rating: ★★★★★</p>
                <input type="file" onchange="updatePicture(event, 'lawyer2')">
            </div>
        </div>
        <div id="criminal" class="lawyer-profile">
            <div class="lawyer">
                <img id="lawyer3" src="uploaded_lawyer_image.jpg" alt="Lawyer 3">
                <h3>Michael Johnson</h3>
                <p>Degree: LLM, Oxford University</p>
                <p>Specialty: Criminal Law</p>
                <p>Rating: ★★★★☆</p>
                <input type="file" onchange="updatePicture(event, 'lawyer3')">
            </div>
        </div>
    </section>
    <footer>
        <p>&copy; 2025 Legal Services Platform | All Rights Reserved</p>
    </footer>
</body>
</html>
