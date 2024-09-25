<html>
<head>
    <meta charset="UTF-8">
    <title>QuadTree</title>
    <style>
        .lang { display: none; }
        .lang-en { display: block; }
        .lang-btn {
            margin: 10px;
            padding: 5px 10px;
            cursor: pointer;
            border: 1px solid #ccc;
            background-color: #f0f0f0;
            display: inline-block;
        }
    </style>
</head>
<body>

<h1>QuadTree</h1>
<p>
    <span class="lang-btn" onclick="setLanguage('en')">English</span>
    <span class="lang-btn" onclick="setLanguage('zh')">中文</span>
</p>

<div id="content">
    <!-- English Version -->
    <div class="lang lang-en">
        <h2>1. Object Pool</h2>
        <h3>1. Initialization and Construction</h3>
        <p>The object pool is created with delegate functions passed in the constructor for creating, acquiring, releasing, and destroying objects. It pre-creates a certain number of objects based on parameters and stores them in an internal collection, ensuring the object pool can provide objects immediately upon initialization. The maximum capacity is determined at this stage to prevent unlimited expansion of the pool.</p>
        
        <h3>2. Object Acquisition</h3>
        <ul>
            <li>When an object is needed, the <code>Get()</code> method retrieves an object from the internal collection. If the pool is empty, it calls the creation function to generate a new object.</li>
            <li>After acquisition, the <code>getFunc</code> delegate is called to perform any necessary initialization or activation, ensuring the object is in the correct state before use.</li>
            <li>The <code>Get()</code> method dynamically tracks the maximum number of active objects for later adjustment.</li>
        </ul>

        <!-- Continue adding English content similarly... -->
    </div>

    <!-- Chinese Version -->
    <div class="lang lang-zh">
        <h2>1. 对象池</h2>
        <h3>1. 初始化与构造</h3>
        <p>对象池在创建时通过构造函数传入了对象的创建、获取、释放、销毁操作的委托函数。构造函数根据参数预先创建一定数量的对象，并将它们存储在内部集合中，确保对象池在初始化后能够立即提供可用对象。最大容量也在此阶段确定，防止池无限膨胀。</p>
        
        <h3>2. 对象获取</h3>
        <ul>
            <li>当需要对象时，<code>Get()</code> 方法会从内部集合中取出一个对象。如果对象池为空，会调用创建函数生成新的对象并返回。</li>
            <li>对象获取后，<code>getFunc</code> 委托被调用，执行任何必要的初始化或激活操作。这样确保对象在被使用前处于正确的状态。</li>
            <li><code>Get()</code> 方法还会动态记录池中最大同时激活的对象数量，方便统计和后续调整。</li>
        </ul>

        <!-- Continue adding Chinese content similarly... -->
    </div>
</div>

<script>
    function setLanguage(lang) {
        // Hide all language sections
        document.querySelectorAll('.lang').forEach(function(element) {
            element.style.display = 'none';
        });

        // Show the selected language
        document.querySelectorAll('.lang-' + lang).forEach(function(element) {
            element.style.display = 'block';
        });
    }

    // Set the default language to English
    setLanguage('en');
</script>

</body>
</html>
