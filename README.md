/* Step 8 & 9: Function to dynamically add tabindex on page load */
function initializeGallery() {
  /* Step 9a: Console log message to verify event trigger */
  console.log("Page loaded: initializeGallery function triggered.");

  /* Step 9b: Get all preview images using querySelectorAll */
  let images = document.querySelectorAll(".preview");

  /* Step 9b & 9c: Loop through each image and add tabindex="0" */
  for (let i = 0; i < images.length; i++) {
    images[i].setAttribute("tabindex", "0");
    console.log("Tabindex added to image " + (i + 1));
  }
}

/* Step 6 & 7: Function triggered by onmouseover and onfocus */
function upDate(previewPic) {
  console.log("Event triggered: mouseover/focus");
  console.log("Alt text:", previewPic.alt);
  console.log("Source URL:", previewPic.src);

  let imageDiv = document.getElementById("image");
  imageDiv.innerHTML = previewPic.alt;
  imageDiv.style.backgroundImage = "url('" + previewPic.src + "')";
}

/* Step 6 & 7: Function triggered by onmouseleave and onblur */
function unDo() {
  let imageDiv = document.getElementById("image");
  imageDiv.style.backgroundImage = "url('')";
  imageDiv.innerHTML = "Hover over an image below to display here.";
}
