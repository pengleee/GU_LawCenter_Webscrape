
# Step 2: Open the Georgetown directory page
driver.get("https://directory.georgetown.edu/")

# Step 3: Input search term for law students (You may need to adjust for specific fields)
search_box = driver.find_element_by_name("search")
search_box.send_keys("law student")
search_box.send_keys(Keys.RETURN)

# Step 4: Wait for results to load (adjust as necessary)
time.sleep(5)

# Step 5: Parse the page content with BeautifulSoup
soup = BeautifulSoup(driver.page_source, "html.parser")

# Step 6: Extract relevant fields
affiliations = []
statuses = []
emails = []
years_and_majors = []

# Adjust the selectors based on the directory's structure
for person in soup.find_all("div", class_="result"):
    affiliation = person.find("div", class_="affiliation").text if person.find("div", class_="affiliation") else None
    status = person.find("div", class_="status").text if person.find("div", class_="status") else None
    email = person.find("div", class_="email").text if person.find("div", class_="email") else None
    year_major = person.find("div", class_="year-major").text if person.find("div", class_="year-major") else None
    
    affiliations.append(affiliation)
    statuses.append(status)
    emails.append(email)
    years_and_majors.append(year_major)

# Step 7: Store the data in a pandas DataFrame and export to CSV
data = {
    "Affiliation": affiliations,
    "Status": statuses,
    "Email": emails,
    "Year_Major": years_and_majors
}
df = pd.DataFrame(data)

# Step 8: Save to CSV
df.to_csv("georgetown_law_students.csv", index=False)

# Close the browser
driver.quit()