# Slider-Based Grading System

| Name          | Slider Value                                                                                 | Number Mapped                        |
| ------------- | -------------------------------------------------------------------------------------------- | ------------------------------------ |
| Example 1     | <input type="range" min="1" max="100" value="50" oninput="updateValue(this)" class="slider"> | <span class="mapped-value">50</span> |
| Example 2     | <input type="range" min="1" max="100" value="75" oninput="updateValue(this)" class="slider"> | <span class="mapped-value">75</span> |
| Add Row Here! | <input type="range" min="1" max="100" value="60" oninput="updateValue(this)" class="slider"> | <span class="mapped-value">60</span> |
|               |                                                                                              |                                      |

---

### Average Slider Value: **<span id="average-value">0</span>**
### Grade: **<span id="grade">U</span>**

---

<script>
function updateValue(slider) {
    const numberCell = slider.nextElementSibling; // Next element is where the mapped value is stored
    numberCell.textContent = slider.value; // Update number
    
    // Calculate the average
    const sliders = document.querySelectorAll('.slider');
    let total = 0;
    sliders.forEach(sl => total += parseInt(sl.value));
    const average = total / sliders.length;
    
    // Update the average display
    document.getElementById('average-value').textContent = average.toFixed(2);
    
    // Map the average to a grade
    const grade = getGrade(average);
    document.getElementById('grade').textContent = grade;
}

function getGrade(value) {
    if (value >= 95) return "A**";
    if (value >= 90) return "A*";
    if (value >= 85) return "A";
    if (value >= 80) return "A-";
    if (value >= 75) return "B";
    if (value >= 70) return "B-";
    if (value >= 65) return "C";
    if (value >= 60) return "C-";
    if (value >= 55) return "D";
    if (value >= 50) return "D-";
    if (value >= 45) return "E";
    if (value >= 40) return "E-";
    return "U";
}
</script>

