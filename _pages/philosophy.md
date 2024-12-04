---
title: "Philosophy: 与中西哲学家对话"
layout: page
permalink: "/philosophy.html"
---

<div class="container">
    <div class="row">
        <!-- 与老子对话 -->
        <div class="col-md-6 mb-4">
            <div class="card h-100 shadow-sm">
                <div class="card-body" style="background: linear-gradient(45deg, #2c3e50, #3498db);">
                    <div class="d-flex align-items-center mb-3">
                        <div class="flex-grow-1">
                            <h2 class="card-title h4 mb-0 text-white">与老子对话</h2>
                            <p class="card-text text-white-50">道可道非常道，名可名、非常名</p>
                        </div>
                        <div class="ml-3">
                            <i class="fas fa-yin-yang fa-2x text-white"></i>
                        </div>
                    </div>
                    <a href="http://124.220.11.240/chat/u0FOzTNnA17z1s9I" target="_blank" class="btn btn-light">开始对话</a>
                </div>
            </div>
        </div>

        <!-- 与孔子对话 -->
        <div class="col-md-6 mb-4">
            <div class="card h-100 shadow-sm">
                <div class="card-body" style="background: linear-gradient(45deg, #c0392b, #e74c3c);">
                    <div class="d-flex align-items-center mb-3">
                        <div class="flex-grow-1">
                            <h2 class="card-title h4 mb-0 text-white">与孔子对话</h2>
                            <p class="card-text text-white-50">有朋自远方来，不亦乐乎</p>
                        </div>
                        <div class="ml-3">
                            <i class="fas fa-book-reader fa-2x text-white"></i>
                        </div>
                    </div>
                    <a href="http://124.220.11.240/chat/TSU7EIXjSAf0NkmT" target="_blank" class="btn btn-light">开始对话</a>
                </div>
            </div>
        </div>

        <!-- 与康德对话 -->
        <div class="col-md-6 mb-4">
            <div class="card h-100 shadow-sm">
                <div class="card-body" style="background: linear-gradient(45deg, #8e44ad, #9b59b6);">
                    <div class="d-flex align-items-center mb-3">
                        <div class="flex-grow-1">
                            <h2 class="card-title h4 mb-0 text-white">与康德对话</h2>
                            <p class="card-text text-white-50">有两种东西，我对它们的思考越是深沉和持久，它们在我心灵中唤起的赞叹和敬畏越是历久弥新，那就是我头上的星空和我心中的道德律</p>
                        </div>
                        <div class="ml-3">
                            <i class="fas fa-star fa-2x text-white"></i>
                        </div>
                    </div>
                    <a href="http://124.220.11.240/chat/7P3zwWsiTP2T0kr9" target="_blank" class="btn btn-light">开始对话</a>
                </div>
            </div>
        </div>

        <!-- 与维特根斯坦对话 -->
        <div class="col-md-6 mb-4">
            <div class="card h-100 shadow-sm">
                <div class="card-body" style="background: linear-gradient(45deg, #27ae60, #2ecc71);">
                    <div class="d-flex align-items-center mb-3">
                        <div class="flex-grow-1">
                            <h2 class="card-title h4 mb-0 text-white">与维特根斯坦对话</h2>
                            <p class="card-text text-white-50">我的语言的边界，就是我的世界的边界</p>
                        </div>
                        <div class="ml-3">
                            <i class="fas fa-language fa-2x text-white"></i>
                        </div>
                    </div>
                    <a href="http://124.220.11.240/chat/4Qu5lFjneqxQcMf9" target="_blank" class="btn btn-light">开始对话</a>
                </div>
            </div>
        </div>
    </div>
</div>

<style>
.card {
    transition: transform 0.2s ease-in-out;
    border-radius: 15px;
    border: none;
    overflow: hidden;
    margin-bottom: 30px;
}
.card:hover {
    transform: translateY(-5px);
    box-shadow: 0 10px 20px rgba(0,0,0,0.2) !important;
}
.card-body {
    padding: 2rem;
    height: 100%;
}
.text-white-50 {
    opacity: 0.8;
    font-size: 0.9rem;
    line-height: 1.4;
}
.shadow-sm {
    box-shadow: 0 5px 15px rgba(0,0,0,0.1) !important;
}
.card-title {
    font-size: 1.5rem;
    font-weight: 600;
    margin-bottom: 0.5rem;
}
.btn {
    border-radius: 20px;
    padding: 8px 20px;
    font-weight: 500;
    transition: all 0.3s ease;
}
.btn:hover {
    transform: translateY(-2px);
    box-shadow: 0 5px 15px rgba(0,0,0,0.1);
}
.fas {
    opacity: 0.9;
}
</style>

<script>
window.addEventListener('load', function() {
    // 初始化所有聊天窗口
    const chatIds = ['laozi', 'kongzi', 'kant', 'wittgenstein'];
    chatIds.forEach(id => {
        window.dify.initChatWidget({
            elementId: id + '-chat',
            configuration: {
                // 这里需要替换成实际的配置
                baseUrl: 'http://124.220.11.240',
                api_key: '你的API密钥',
                chat_context_id: id
            }
        });
    });
});
</script> 