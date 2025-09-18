用户表: 用户信息
CREATE TABLE users (
    id INT AUTO_INCREMENT PRIMARY KEY, -- 用户ID，主键
    username VARCHAR(50) NOT NULL UNIQUE, -- 用户名
    phone VARCHAR(11) NOT NULL UNIQUE, -- 手机号
    email VARCHAR(100) UNIQUE, -- 邮箱（唯一）
    address VARCHAR(200), -- 收货地址
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP -- 创建时间
);

-----
产品表: 商品信息
CREATE TABLE products (
    id INT AUTO_INCREMENT PRIMARY KEY, -- 商品ID，主键
    product_name VARCHAR(100) NOT NULL, -- 商品名称
    price DECIMAL(10,2) NOT NULL CHECK (price > 0), -- 商品价格
    stock INT NOT NULL CHECK (stock >= 0), -- 库存
    status ENUM('上架', '下架') DEFAULT '上架', -- 商品状态
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP -- 创建时间
);

-----
订单表: 订单信息
CREATE TABLE orders (
    id INT AUTO_INCREMENT PRIMARY KEY, -- 订单ID
    user_id INT NOT NULL, -- 用户ID
    order_no VARCHAR(20) NOT NULL UNIQUE, -- 订单编号
    total_amount DECIMAL(10,2) NOT NULL, -- 总金额
    status ENUM('已付款', '已发货', '已完成', '已取消') DEFAULT '已付款', -- 状态
    order_time TIMESTAMP DEFAULT CURRENT_TIMESTAMP, -- 下单时间
    FOREIGN KEY (user_id) REFERENCES users(id) ON DELETE CASCADE
);

-----
订单明细表: 订单中的商品明细
CREATE TABLE order_items (
    id INT AUTO_INCREMENT PRIMARY KEY, -- 明细ID
    order_id INT NOT NULL, -- 订单ID
    product_id INT NOT NULL, -- 商品ID
    quantity INT NOT NULL CHECK (quantity > 0), -- 数量
    unit_price DECIMAL(10,2) NOT NULL, -- 单价
    total_price DECIMAL(10,2) AS (quantity * unit_price) STORED, -- 总价
    FOREIGN KEY (order_id) REFERENCES orders(id) ON DELETE CASCADE,
    FOREIGN KEY (product_id) REFERENCES products(id) ON DELETE CASCADE
);