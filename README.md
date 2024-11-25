# Kod

import React, { useState } from 'react';

const BookingSystem = () => {
  // En array med olika tider
  const times = ['09:00', '10:00', '11:00', '12:00', '13:00', '14:00'];

  // Håller koll på vilken tid som är bokad
  const [bookedTime, setBookedTime] = useState(null);

  // Funktion för att boka en tid
  const handleBooking = (time) => {
    setBookedTime(time);
  };

  return (
    <div>
      <h1>Bokningssystem</h1>
      <table>
        <thead>
          <tr>
            <th>Tid</th>
            <th>Tillgänglig</th>
          </tr>
        </thead>
        <tbody>
          {times.map((time) => (
            <tr key={time}>
              <td>{time}</td>
              <td>
                {/* Om tiden är bokad, visa en meddelande annars en bokningsknapp */}
                {bookedTime === time ? (
                  <span>Bokad</span>
                ) : (
                  <button onClick={() => handleBooking(time)}>Boka</button>
                )}
              </td>
            </tr>
          ))}
        </tbody>
      </table>
      {bookedTime && <p>Du har bokat: {bookedTime}</p>}
    </div>
  );
};

export default BookingSystem;
