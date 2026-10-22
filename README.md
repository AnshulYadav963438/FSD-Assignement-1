
const EventEmitter = require('events');

const eventEmitter = new EventEmitter();

function createOrder() {
    const order = {
        orderId: 101,
        product: 'Laptop',
        price: 50000
    };

    console.log('Order created successfully!');
    eventEmitter.emit('orderCreated', order);
}

eventEmitter.on('orderCreated', (order) => {
    console.log('Email sent for Order ID:', order.orderId);
});

eventEmitter.on('orderCreated', (order) => {
    console.log('Inventory updated for:', order.product);
});

eventEmitter.on('orderCreated', (order) => {
    console.log('Notification sent to customer.');
});

createOrder();
