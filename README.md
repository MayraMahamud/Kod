# Kod


    <select onChange={handleRoomChange}
        value={selectedRoom}>
            <option value="">Mötesrum</option>
            {rooms.map((room) => (
                <option key={room.date} 
                value={rooms.Name}>
                    {rooms.name} ({rooms.capacity} personer)

                </option>
            ))}
        </select>
