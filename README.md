
Support Center
快速排查
联系售后
EN
亚马逊订单优先支持
先别急着退货：3步快修或快速换新
多数问题5分钟内解决。我们承诺平均2小时内响应，并提供配件补寄与使用指导。

开始快速排查
直接联系售后
🛒 支持亚马逊订单
🔒 隐私保护
⚡ 5分钟快修
🧰 配件补寄
合规声明：您随时可以通过亚马逊发起退货，我们的支持仅旨在更快、更合适地解决问题，不含任何换评/激励。

Live KPI
2h
平均响应
40%
自助解决率
-25%
退货率下降
<!-- Quick Fix Wizard -->
<section id="quickfix">
  <h2><span class="zh">快速排查向导</span><span class="en">Quick Fix Wizard</span></h2>
  <p class="muted">
    <span class="zh">选择产品与问题，我们将给出1‑2步快修方案。若仍未解决，1分钟提交表单，我们优先处理。</span>
    <span class="en">Choose your product and issue for 1‑2 step fixes. If it persists, submit the form in 1 minute—we’ll prioritize your case.</span>
  </p>
  <div class="grid cols-2">
    <div class="card">
      <label class="muted"><span class="zh">产品</span><span class="en">Product</span></label>
      <select id="product" class="input" onchange="onProductChange()">
        <option value="airpods-pro-1-wireless">Apple AirPods Pro (1st Gen) – Wireless Charging Case (Lightning, Renewed)</option>
        <option value="airpods-pro-1-magsafe">Apple AirPods Pro (1st Gen) – MagSafe Charging Case (Renewed)</option>
        <option value="airpods-pro-2-magsafe">Apple AirPods Pro (2nd Gen) – MagSafe Case (Lightning/USB‑C)</option>
      </select>

      <div style="height:10px"></div>
      <label class="muted"><span class="zh">问题类别</span><span class="en">Issue</span></label>
      <div id="issues" class="row-gap">
        <!-- buttons injected -->
      </div>

      <div style="height:10px"></div>
      <div class="steps" id="steps"></div>

      <div id="fixResult" style="display:none;margin-top:12px">
        <div class="success">
          <span class="zh">已提供解决步骤。若问题仍存在，请点击下方“联系售后”，提交表单时会自动带入您已尝试的步骤。</span>
          <span class="en">We’ve provided targeted steps. If the issue persists, click “Contact Support”; your tried steps will be carried over.</span>
        </div>
        <div style="height:10px"></div>
        <button class="btn primary" onclick="goContact()">
          <span class="zh">联系售后</span><span class="en">Contact Support</span>
        </button>
      </div>
    </div>

    <div class="card">
      <div class="label">
        <span class="zh">退货前自检</span><span class="en">Pre‑return checklist</span>
      </div>
      <ul class="list">
        <li><span class="zh">已重置并重新配对（盒背按钮按住约15秒至白灯）</span><span class="en">Reset and re‑pair (hold case back button ~15s to white flash)</span></li>
        <li><span class="zh">清洁充电触点与仓位，耳机磁吸到位并短亮</span><span class="en">Contacts/wells cleaned; buds seat magnetically and briefly light</span></li>
        <li><span class="zh">贴合度测试通过；尝试不同耳塞尺寸验证ANC/通透</span><span class="en">Fit Test passed; tried different eartip sizes for ANC/Transparency</span></li>
        <li><span class="zh">了解本款为标准Qi无线充（如适用），非MagSafe磁吸对位</span><span class="en">Aware: standard Qi wireless (if applicable), not MagSafe snap‑align</span></li>
        <li><span class="zh">已用不同线缆/充电器交叉测试</span><span class="en">Tried different cables/adapters</span></li>
      </ul>
      <div style="height:10px"></div>
      <p class="muted">
        <span class="zh">提示：您始终可以通过亚马逊发起退货；我们仅提供更快的解决方案与换新通道。</span>
        <span class="en">Note: You can always return via Amazon; we simply offer faster solutions or replacements.</span>
      </p>
    </div>
  </div>
</section>

<!-- Contact Support -->
<section id="contact">
  <h2><span class="zh">联系售后</span><span class="en">Contact Support</span></h2>
  <div class="grid cols-2">
    <div class="card">
      <form id="supportForm" onsubmit="return handleSubmit(event)">
        <div class="row-gap">
          <div style="flex:1;min-width:180px">
            <label class="muted"><span class="zh">姓名</span><span class="en">Name</span></label>
            <input class="input" name="name" required placeholder="Your name" />
          </div>
          <div style="flex:1;min-width:220px">
            <label class="muted">Email</label>
            <input class="input" type="email" name="email" required placeholder="you@email.com" />
          </div>
        </div>
        <div style="height:10px"></div>
        <label class="muted"><span class="zh">亚马逊订单号</span><span class="en">Amazon Order ID</span> <span class="hint">112‑XXXXXXX‑XXXXXXX</span></label>
        <input class="input" name="orderId" required pattern="\\d{3}-\\d{7}-\\d{7}" placeholder="123-1234567-1234567" />
        <div style="height:10px"></div>
        <div class="row-gap">
          <div style="flex:1;min-width:220px">
            <label class="muted"><span class="zh">产品</span><span class="en">Product</span></label>
            <select class="input" name="product" id="formProduct"></select>
          </div>
          <div style="flex:1;min-width:220px">
            <label class="muted"><span class="zh">问题类型</span><span class="en">Issue</span></label>
            <select class="input" name="issue" id="formIssue"></select>
          </div>
        </div>
        <div style="height:10px"></div>
        <label class="muted"><span class="zh">已尝试步骤</span><span class="en">Steps tried</span></label>
        <div id="triedSteps" class="row-gap"></div>
        <div style="height:10px"></div>
        <label class="muted"><span class="zh">问题描述</span><span class="en">Description</span></label>
        <textarea class="input" name="desc" placeholder="Describe the issue, LED behavior, environment, etc." required></textarea>
        <div style="height:10px"></div>
        <label class="muted"><span class="zh">上传照片/视频（最多3个）</span><span class="en">Upload photos/videos (max 3)</span></label>
        <input class="input" type="file" id="files" accept="image/*,video/*" multiple />
        <div style="height:10px"></div>
        <label><input type="checkbox" id="consent" required /> <span class="muted zh">我同意仅为售后目的使用我的信息</span><span class="muted en">I agree to use my info for support purposes only</span></label>
        <div style="height:14px"></div>
        <button class="btn primary" type="submit">
          <span class="zh">提交并创建工单</span><span class="en">Submit & create ticket</span>
        </button>
        <div style="height:10px"></div>
        <div id="formMsg"></div>
      </form>
    </div>
    <div class="card">
      <div class="label"><span class="zh">我们如何帮助您</span><span class="en">How we help</span></div>
      <ul class="list">
        <li><span class="zh">平均2小时内响应（工作日）</span><span class="en">Avg response under 2 hours (business days)</span></li>
        <li><span class="zh">技术问题5分钟内自助解决率>40%</span><span class="en">Over 40% self‑solve in 5 minutes</span></li>
        <li><span class="zh">配件补寄、远程指导或快速换新</span><span class="en">Parts replacement, remote guidance or fast replacement</span></li>
        <li><span class="zh">尊重亚马逊退货政策，绝不设置障碍</span><span class="en">Respect Amazon returns; no obstacles</span></li>
      </ul>
      <div style="height:10px"></div>
      <div class="label"><span class="zh">其他联系方式</span><span class="en">Other channels</span></div>
      <p class="muted">Email: support@example.com · WhatsApp/WeChat: on request</p>
    </div>
  </div>
</section>

<!-- FAQ -->
<section id="faq">
  <h2>FAQ</h2>
  <div class="grid">
    <div class="faq-item">
      <div class="faq-q" onclick="toggleFaq(this)">
        <b class="zh">我应通过亚马逊退货还是先联系你们？</b>
        <b class="en">Should I return via Amazon or contact you first?</b>
      </div>
      <div class="faq-a">
        <p class="zh">您可以随时通过亚马逊发起退货；但技术问题通常能在数分钟内解决或提供快速换新，建议先联系我们。</p>
        <p class="en">You can start an Amazon return anytime; however, most technical issues are fixed in minutes or replaced fast—contact us first.</p>
      </div>
    </div>
    <div class="faq-item">
      <div class="faq-q" onclick="toggleFaq(this)">
        <b class="zh">AirPods Pro 第一代与第二代有哪些差异？</b>
        <b class="en">Differences between AirPods Pro 1st and 2nd gen?</b>
      </div>
      <div class="faq-a">
        <p class="zh">第一代无耳柄滑动调音量，充电盒无扬声器/挂绳孔/精确查找；第二代具备这些功能。</p>
        <p class="en">1st gen lacks stem volume swipe and case speaker/lanyard/Precision Finding; 2nd gen includes these.</p>
      </div>
    </div>
    <div class="faq-item">
      <div class="faq-q" onclick="toggleFaq(this)">
        <b class="zh">无线充电无法“吸附”是坏了吗？</b>
        <b class="en">Wireless charging doesn’t “snap”—is it faulty?</b>
      </div>
      <div class="faq-a">
        <p class="zh">第一代标准无线充电盒为Qi充电，不是MagSafe磁吸对位；请在Qi板上平放并对齐线圈。</p>
        <p class="en">1st gen standard case supports Qi charging, not MagSafe snap alignment; place flat and align coils.</p>
      </div>
    </div>
    <div class="faq-item">
      <div class="faq-q" onclick="toggleFaq(this)">
        <b class="zh">Renewed/翻新说明</b>
        <b class="en">About Renewed</b>
      </div>
      <div class="faq-a">
        <p class="zh">翻新产品经过专业清洁、检测与必要更换；功能完好，外观可能有轻微痕迹；保障以平台政策为准。</p>
        <p class="en">Renewed units are professionally cleaned/tested with necessary part replacements; fully functional, minor cosmetic wear possible; coverage per marketplace policy.</p>
      </div>
    </div>
  </div>
</section>

<!-- Policies -->
<section id="policies">
  <h2><span class="zh">保修与隐私</span><span class="en">Warranty & Privacy</span></h2>
  <div class="card">
    <p class="zh">我们遵守亚马逊平台规则与当地法律，对您的信息仅用于售后支持。需要时可申请删除数据。详见隐私政策与使用条款。</p>
    <p class="en">We follow Amazon rules and local laws. Your data is used only for support. You may request deletion. See Privacy Policy and Terms.</p>
  </div>
</section>

<footer>
  <div class="wrap">
    <div class="row" style="justify-content:space-between;align-items:flex-start">
      <div>
        <div><b>Support Center</b></div>
        <div class="muted">© 2025 · All rights reserved</div>
      </div>
      <div class="muted">
        <div><span class="zh">需要企业定制？</span><span class="en">Need custom?</span> hello@example.com</div>
      </div>
    </div>
  </div>
</footer>
