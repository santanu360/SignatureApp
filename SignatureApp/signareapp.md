# Signature App

This project is a web-based application that allows users to draw, save, and retrieve their signatures. The application provides options to customize the text color, background color, and font size of the signature. Users can clear the canvas, save their signature as an image, and retrieve previously saved signatures.

## Features

- **Text Color Picker**: Allows users to select the color of the text they draw on the canvas.
- **Background Color Picker**: Allows users to change the background color of the canvas.
- **Font Size Selector**: Provides options to change the font size of the text drawn on the canvas.
- **Clear Button**: Clears the canvas.
- **Save & Download Button**: Saves the current state of the canvas and allows users to download it as an image.
- **Retrieve Saved Signature Button**: Retrieves and displays a previously saved signature from local storage.

## Technologies Used

- HTML
- CSS
- JavaScript
- Bootstrap

## How to Use

1. Open the application in a web browser.
2. Use the color pickers to select the text and background colors.
3. Use the font size selector to choose the desired font size.
4. Draw on the canvas using the mouse.
5. Click the "Clear" button to clear the canvas.
6. Click the "Save & Download" button to save the current signature and download it as an image.
7. Click the "Retrieve Saved Signature" button to retrieve and display a previously saved signature.

## Project Explanation

This project is a simple web application designed to allow users to create and manage their digital signatures. The main components of the application include a canvas element for drawing, input elements for customizing the drawing, and buttons for clearing, saving, and retrieving signatures.

The canvas element is used to capture the user's drawing using mouse events. The application listens for `mousedown`, `mousemove`, and `mouseup` events to draw lines on the canvas. The color and font size of the drawing can be customized using the color pickers and font size selector.

The "Clear" button clears the canvas by calling the `clearRect` method on the canvas context. The "Save & Download" button saves the current state of the canvas to local storage and allows the user to download it as an image. The "Retrieve Saved Signature" button retrieves the saved signature from local storage and displays it on the canvas.

## Interview Questions

1. **What is the purpose of the `canvas` element in this project?**
  - The `canvas` element is used to provide a drawing area where users can create their signatures. It captures mouse events to draw lines based on user input.

2. **How does the application handle drawing on the canvas?**
  - The application listens for `mousedown`, `mousemove`, and `mouseup` events on the canvas. When the user presses the mouse button (`mousedown`), it starts drawing. As the user moves the mouse (`mousemove`), it draws lines on the canvas. When the user releases the mouse button (`mouseup`), it stops drawing.

3. **How can users customize the text color and background color of the canvas?**
  - Users can customize the text color using the "Text Color Picker" input element and the background color using the "Background" input element. The application updates the canvas context's `strokeStyle` and `fillStyle` properties based on the selected colors.

4. **What is the purpose of the `localStorage` in this project?**
  - `localStorage` is used to save the current state of the canvas as a data URL. This allows the application to retrieve and display the saved signature even after the page is reloaded.

5. **How does the application save and retrieve the signature?**
  - The application saves the signature by converting the canvas content to a data URL using the `toDataURL` method and storing it in `localStorage`. To retrieve the signature, it loads the data URL from `localStorage`, creates an image element, and draws the image on the canvas.

6. **What libraries or frameworks are used in this project?**
  - The project uses Bootstrap for styling and layout. The rest of the functionality is implemented using vanilla HTML, CSS, and JavaScript.