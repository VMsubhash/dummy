
# Formulas for Face Shape and Fat/Thin Detection

---

## **Face Shape Detection**

1. **Jaw Width**:  
   ```math
   \text{Width} = \sqrt{(\text{jaw}[0].x - \text{jaw}[-1].x)^2 + (\text{jaw}[0].y - \text{jaw}[-1].y)^2}
   ```

2. **Face Height**:  
   ```math
   \text{Height} = \sqrt{(\text{landmarks.part}(27).x - \text{jaw}[8].x)^2 + (\text{landmarks.part}(27).y - \text{jaw}[8].y)^2}
   ```

3. **Aspect Ratio**:  
   ```math
   \text{Ratio} = \frac{\text{Width}}{\text{Height}}
   ```

4. **Face Shape Categories**:
   - **Oval**: \( \text{Ratio} < 0.85 \)
   - **Round**: \( 0.85 \leq \text{Ratio} < 1.0 \)
   - **Square**: \( 1.0 \leq \text{Ratio} < 1.2 \)
   - **Rectangular**: \( \text{Ratio} \geq 1.2 \)

---

## **Fat or Thin Detection**

1. **Cheekbone Width**:  
   ```math
   \text{Cheekbone Width} = \sqrt{(\text{jaw}[3].x - \text{jaw}[13].x)^2 + (\text{jaw}[3].y - \text{jaw}[13].y)^2}
   ```

2. **Face Height**:  
   *(Same formula as in the face shape detection)*
   ```math
   \text{Height} = \sqrt{(\text{landmarks.part}(27).x - \text{jaw}[8].x)^2 + (\text{landmarks.part}(27).y - \text{jaw}[8].y)^2}
   ```

3. **Cheekbone to Height Ratio**:  
   ```math
   \text{Ratio} = \frac{\text{Cheekbone Width}}{\text{Height}}
   ```

4. **Fat/Thin Categories**:
   - **Fat**: \( \text{Ratio} > 1.2 \)
   - **Normal**: \( 1.0 < \text{Ratio} \leq 1.2 \)
   - **Thin**: \( \text{Ratio} \leq 1.0 \)

---
