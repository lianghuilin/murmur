- html
```
<!-- 表单要用form标签包含 -->
<form class="layui-form" action="">
  <div class="layui-card">
    <div class="layui-card-header">
      <span class="card-header-title">事件基本信息</span>
      <div class="card-header-btn">
          <!-- 提交按钮需要设置lay-submit属性，定义lay-filter(类似id的命名区分) -->
          <button type="button"  class="layui-btn layui-btn-sm"
            lay-submit lay-filter="eventHeadForm">创建事件</button>
      </div>
    </div>
    <div class="layui-card-body">
      <div class="layui-row">
        <div class="layui-col-md4">
          <div class="layui-form-item">
              <div class="layui-inline">
                  <label class="layui-form-label">事件名称</label>
                  <div class="layui-input-inline">
                      <!-- 表单控件需要设置lay-verify属性  -->
                      <input type="text" class="layui-input"
                        id="eventName" lay-verify="required"
                        autocomplete="off"  placeholder="事件名称，必填" >
                  </div>
              </div>
          </div>
        </div>
        <div class="layui-col-md4">
          <div class="layui-form-item">
              <div class="layui-inline">
                  <label class="layui-form-label">事件类型</label>
                  <div class="layui-input-inline">
                      <select class="layui-input" id="eventType" lay-verify="required" lay-filter="eventType">
                          <option value="限时促销设置" disabled>限时促销设置</option>
                          <option value="门店装修暂停" disabled>门店装修暂停</option>
                          <option value="通用物料停用" disabled>通用物料停用</option>
                          <option value="新品上架(固定值)" disabled>新品上架(固定值)</option>
                          <option value="新品上架(参考旧品)" disabled>新品上架(参考旧品)</option>
                          <option value="临时参数调整" selected>临时参数调整</option>
                      </select>
                  </div>
              </div>
          </div>
          <div class="layui-col-md4">
            <div class="layui-form-item">
                <div class="layui-inline">
                    <label class="layui-form-label">起止日期</label>
                    <div class="layui-input-inline">
                        <input type="text" autocomplete="off" class="layui-input"
                        id="eventDateRange" lay-verify="required"
                            placeholder="选择事件影响的时间范围">
                    </div>
                </div>
            </div>
          </div>
        </div>
      </div>
    </div>
</form>
```
- js
```
<script>
layui.define(["form"],function(e){

  var form = layui.form;


  e('lay_form_demo',{});
})
</script>
```

## 参考资料
- https://www.layui.com/doc/modules/form.html