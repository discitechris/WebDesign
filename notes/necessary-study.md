# Necessary Study

## localStorage

Learn about localStorage which is built into Browsers. which can save data actively

```javascript
function updateSelectedCount() {
  const selectedSeats = document.querySelectorAll('.row .seat.selected');

  const seatsIndex = [...selectedSeats].map(seat => [...seats].indexOf(seat));

  localStorage.setItem('selectedSeats', JSON.stringify(seatsIndex));

  const selectedSeatsCount = selectedSeats.length;

  count.innerText = selectedSeatsCount;
  total.innerText = selectedSeatsCount * ticketPrice;
}
```

localStorage.setItem doesnt store arrays so need to stringify

```javascript
function populateUI() {
  const selectedSeats = JSON.parse(localStorage.getItem("selectSeats"));
  console.log(selectedSeats);
  if (selectedSeats !== null && selectedSeats.length > 0) {
    seats.forEach((seat, index) => {
      if (selectedSeats.indexOf(index) > -1) {
        seat.classList.add("selected");
      }
    });
    };
```

localStorage.getItem returns string so need to parse it back to array.

