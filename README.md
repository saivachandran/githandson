echo "# terraform-test" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin git@github.com:saivachandran/terraform-test.git
git push -u origin main
