# Personal Website

![Project Banner](/static/images/bytes-guide.png)

This is a personal website built using [Hugo](https://gohugo.io/), a fast and flexible static site generator. The project includes various sections such as a blog, portfolio, and more.

## Folder Structure

- **`layouts/`**: Contains the HTML templates for the website.
- **`public/`**: The output folder where the generated static files are stored.
- **`static/`**: Contains static assets like images, CSS, and JavaScript files.
- **`content/`**: The markdown files for the website's content (e.g., blog posts, portfolio items).
- **`themes/`**: The theme used for the website.
- **`config.toml`**: The main configuration file for the Hugo project.

## How to Run the Project

1. **Install Hugo**: Follow the [official installation guide](https://gohugo.io/getting-started/installing/).
2. **Clone the Repository**:
   ```bash
   git clone https://github.com/vincent-buchner/bytes-guide.git
   cd bytes-guide
   ```
3. **Run the Development Server**:

   ```bash
   hugo server
   ```

   The website will be available at `http://localhost:1313/`.

4. **Build the Static Files**:
   ```bash
   hugo
   ```
   The generated files will be in the `public/` directory.

## License

This project is licensed under the MIT License. Feel free to use and modify it as needed.
