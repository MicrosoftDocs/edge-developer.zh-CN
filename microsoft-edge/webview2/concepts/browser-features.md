---
<span data-ttu-id="59948-101">description： Microsoft Edge and WebView2 title之间的功能差异： Microsoft Edge 和 WebView2 作者之间的功能差异： MSEdgeTeam ms.author： msedgedevrel ms.date： 05/06/2021 ms.topic： conceptual ms.prod： microsoft-edge ms.technology： webview keywords： IWebView2， IWebView2WebView、WebView2、webview、wpf 应用、wpf、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、edge html no-loc：</span><span class="sxs-lookup"><span data-stu-id="59948-101">description: Feature differences between Microsoft Edge and WebView2 title: Feature differences between Microsoft Edge and WebView2 author: MSEdgeTeam ms.author: msedgedevrel ms.date: 05/06/2021 ms.topic: conceptual ms.prod: microsoft-edge ms.technology: webview keywords: IWebView2, IWebView2WebView, WebView2, webview, wpf apps, wpf, edge, ICoreWebView2, ICoreWebView2Host, browser control, edge html no-loc:</span></span>
- <span data-ttu-id="59948-102">"Autofill for Addresses"</span><span class="sxs-lookup"><span data-stu-id="59948-102">"Autofill for Addresses"</span></span>
- <span data-ttu-id="59948-103">"Autofill for Passwords"</span><span class="sxs-lookup"><span data-stu-id="59948-103">"Autofill for Passwords"</span></span>
- <span data-ttu-id="59948-104">"Autofill for Payments""</span><span class="sxs-lookup"><span data-stu-id="59948-104">"Autofill for Payments""</span></span>
- <span data-ttu-id="59948-105">"Browser Extensions""</span><span class="sxs-lookup"><span data-stu-id="59948-105">"Browser Extensions""</span></span>
- <span data-ttu-id="59948-106">"Browser Task Manager"</span><span class="sxs-lookup"><span data-stu-id="59948-106">"Browser Task Manager"</span></span>
- <span data-ttu-id="59948-107">"Collections"</span><span class="sxs-lookup"><span data-stu-id="59948-107">"Collections"</span></span>
- <span data-ttu-id="59948-108">"Continue-where-I-left-off prompt"</span><span class="sxs-lookup"><span data-stu-id="59948-108">"Continue-where-I-left-off prompt"</span></span>
- <span data-ttu-id="59948-109">"Downloads"</span><span class="sxs-lookup"><span data-stu-id="59948-109">"Downloads"</span></span>
- <span data-ttu-id="59948-110">"Edge Shopping"</span><span class="sxs-lookup"><span data-stu-id="59948-110">"Edge Shopping"</span></span>
- <span data-ttu-id="59948-111">"Family Safety"</span><span class="sxs-lookup"><span data-stu-id="59948-111">"Family Safety"</span></span>
- <span data-ttu-id="59948-112">"Favorites"</span><span class="sxs-lookup"><span data-stu-id="59948-112">"Favorites"</span></span>
- <span data-ttu-id="59948-113">"Hotkeys"</span><span class="sxs-lookup"><span data-stu-id="59948-113">"Hotkeys"</span></span>
- <span data-ttu-id="59948-114">"IE Mode"</span><span class="sxs-lookup"><span data-stu-id="59948-114">"IE Mode"</span></span>
- <span data-ttu-id="59948-115">"Immersive Reader"</span><span class="sxs-lookup"><span data-stu-id="59948-115">"Immersive Reader"</span></span>
- <span data-ttu-id="59948-116">"Intrusive Ads"</span><span class="sxs-lookup"><span data-stu-id="59948-116">"Intrusive Ads"</span></span>
- <span data-ttu-id="59948-117">"Read Aloud"</span><span class="sxs-lookup"><span data-stu-id="59948-117">"Read Aloud"</span></span>
- <span data-ttu-id="59948-118">"Smart Screen"</span><span class="sxs-lookup"><span data-stu-id="59948-118">"Smart Screen"</span></span>
- <span data-ttu-id="59948-119">"Translate"</span><span class="sxs-lookup"><span data-stu-id="59948-119">"Translate"</span></span>
- <span data-ttu-id="59948-120">"Tracking Prevention"</span><span class="sxs-lookup"><span data-stu-id="59948-120">"Tracking Prevention"</span></span>
- <span data-ttu-id="59948-121">"Profile and Identity"</span><span class="sxs-lookup"><span data-stu-id="59948-121">"Profile and Identity"</span></span>
- <span data-ttu-id="59948-122">"Web Payment API"</span><span class="sxs-lookup"><span data-stu-id="59948-122">"Web Payment API"</span></span>
- <span data-ttu-id="59948-123">"Windows Defender Application Guard"</span><span class="sxs-lookup"><span data-stu-id="59948-123">"Windows Defender Application Guard"</span></span>
- <span data-ttu-id="59948-124">"edge:// URLs"</span><span class="sxs-lookup"><span data-stu-id="59948-124">"edge:// URLs"</span></span>

---
# <a name="browser-feature-differences-between-microsoft-edge-and-webview2"></a><span data-ttu-id="59948-125">浏览器功能与 webView2 Microsoft Edge差异</span><span class="sxs-lookup"><span data-stu-id="59948-125">Browser feature differences between Microsoft Edge and WebView2</span></span>  

<span data-ttu-id="59948-126">WebView2 基于新Microsoft Edge浏览器。</span><span class="sxs-lookup"><span data-stu-id="59948-126">WebView2 is based on the new Microsoft Edge browser.</span></span>  <span data-ttu-id="59948-127">你有机会将功能从浏览器扩展到基于 WebView2 的应用，这很有用。</span><span class="sxs-lookup"><span data-stu-id="59948-127">You have the opportunity to extend features from the browser to WebView2-based apps, which is useful.</span></span>  <span data-ttu-id="59948-128">但是，由于 WebView2 不限于类似浏览器的应用，因此需要修改或删除一些浏览器功能。</span><span class="sxs-lookup"><span data-stu-id="59948-128">However, since WebView2 isn't limited to browser-like apps, there are some browser features that need to be modified or removed.</span></span>  <span data-ttu-id="59948-129">本文提供以下信息。</span><span class="sxs-lookup"><span data-stu-id="59948-129">This article provides the following information.</span></span>  

*   <span data-ttu-id="59948-130">修改后的浏览器功能和支持信息。</span><span class="sxs-lookup"><span data-stu-id="59948-130">The modified browser features and supporting information.</span></span>   
*   <span data-ttu-id="59948-131">启用或关闭功能的功能。</span><span class="sxs-lookup"><span data-stu-id="59948-131">The ability to turn on or off the feature.</span></span>  
*   <span data-ttu-id="59948-132">有关键盘快捷方式的指南。</span><span class="sxs-lookup"><span data-stu-id="59948-132">Guidance on keyboard shortcuts.</span></span>  
    
## <a name="design-guidelines"></a><span data-ttu-id="59948-133">设计指南</span><span class="sxs-lookup"><span data-stu-id="59948-133">Design guidelines</span></span>  

<span data-ttu-id="59948-134">在 WebView2 上下文中，浏览器功能遵循以下设计准则。</span><span class="sxs-lookup"><span data-stu-id="59948-134">In the context of WebView2, browser features adhere to the following design guidelines.</span></span>  

*   <span data-ttu-id="59948-135">大多数功能在 WebView2 和 webView2 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="59948-135">Most features work the same in WebView2 and Microsoft Edge.</span></span>  <span data-ttu-id="59948-136">如果功能在 WebView2 上下文中不起作用或出于其他原因，则功能会修改或关闭。</span><span class="sxs-lookup"><span data-stu-id="59948-136">If a feature doesn't make sense in the context of WebView2 or for other reasons, the feature is modified or turned off.</span></span> 
*   <span data-ttu-id="59948-137">WebView2 功能不包括Microsoft Edge品牌。</span><span class="sxs-lookup"><span data-stu-id="59948-137">WebView2 features don't include Microsoft Edge branding.</span></span>  
    
## <a name="features"></a><span data-ttu-id="59948-138">功能</span><span class="sxs-lookup"><span data-stu-id="59948-138">Features</span></span>  

<span data-ttu-id="59948-139">下表显示了与浏览器浏览器不同的 WebView2 Microsoft Edge功能。</span><span class="sxs-lookup"><span data-stu-id="59948-139">The following table displays the WebView2 features that differ from the Microsoft Edge browser.</span></span>   

*   <span data-ttu-id="59948-140">**默认** 状态指示功能是新 WebView2 实例上默认体验的一部分。</span><span class="sxs-lookup"><span data-stu-id="59948-140">**Default state** indicates that the feature is part of the default experience on a new WebView2 instance.</span></span>  
*   <span data-ttu-id="59948-141">**可** 配置指示可以使用 WebView2 API 或命令行开关打开或关闭该功能。</span><span class="sxs-lookup"><span data-stu-id="59948-141">**Configurable** indicates that you may turn on or off the feature using WebView2 APIs or command-line switches.</span></span>  
    
> [!NOTE]  
> <span data-ttu-id="59948-142">本文不介绍使用命令行开关修改功能。</span><span class="sxs-lookup"><span data-stu-id="59948-142">This article doesn't cover modifying features using command-line switches.</span></span>  <span data-ttu-id="59948-143">有关使用命令行开关打开和关闭功能的信息，请导航到"命令行Chromium[列表。][PeterExperimentsChromiumCommandLineSwitches]</span><span class="sxs-lookup"><span data-stu-id="59948-143">For more information about turning on and off features with command-line switches, navigate to [List of Chromium Command Line Switches][PeterExperimentsChromiumCommandLineSwitches].</span></span>  
    
| <span data-ttu-id="59948-144">功能</span><span class="sxs-lookup"><span data-stu-id="59948-144">Feature</span></span> | <span data-ttu-id="59948-145">默认状态</span><span class="sxs-lookup"><span data-stu-id="59948-145">Default state</span></span> | <span data-ttu-id="59948-146">可配置</span><span class="sxs-lookup"><span data-stu-id="59948-146">Configurable</span></span> | <span data-ttu-id="59948-147">详细信息</span><span class="sxs-lookup"><span data-stu-id="59948-147">Details</span></span> |  
|:--- |:--- |:--- | :--- |  
| Autofill for Addresses | <span data-ttu-id="59948-148">开</span><span class="sxs-lookup"><span data-stu-id="59948-148">On</span></span> | <span data-ttu-id="59948-149">是</span><span class="sxs-lookup"><span data-stu-id="59948-149">Yes</span></span> | <span data-ttu-id="59948-150">默认情况下，此功能已打开，可以使用 WebView2 自动填充 API 将其打开或关闭。</span><span class="sxs-lookup"><span data-stu-id="59948-150">This feature is turned on by default, you may turn it on or off using WebView2 Autofill APIs.</span></span>  |  
| Autofill for Passwords | <span data-ttu-id="59948-151">开</span><span class="sxs-lookup"><span data-stu-id="59948-151">On</span></span> | <span data-ttu-id="59948-152">是</span><span class="sxs-lookup"><span data-stu-id="59948-152">Yes</span></span> | <span data-ttu-id="59948-153">默认情况下，此功能已打开，可以使用 WebView2 自动填充 API 将其打开或关闭。</span><span class="sxs-lookup"><span data-stu-id="59948-153">This feature is turned on by default, you may turn it on or off using WebView2 Autofill APIs.</span></span>  |  
| <span data-ttu-id="59948-154">付款自动填充</span><span class="sxs-lookup"><span data-stu-id="59948-154">Autofill for Payments</span></span> | <span data-ttu-id="59948-155">关闭</span><span class="sxs-lookup"><span data-stu-id="59948-155">Off</span></span> | <span data-ttu-id="59948-156">否</span><span class="sxs-lookup"><span data-stu-id="59948-156">No</span></span> | <span data-ttu-id="59948-157">此功能已关闭。</span><span class="sxs-lookup"><span data-stu-id="59948-157">This feature is turned off.</span></span>  |  
| <span data-ttu-id="59948-158">浏览器扩展</span><span class="sxs-lookup"><span data-stu-id="59948-158">Browser Extensions</span></span> | <span data-ttu-id="59948-159">关闭</span><span class="sxs-lookup"><span data-stu-id="59948-159">Off</span></span> | <span data-ttu-id="59948-160">否</span><span class="sxs-lookup"><span data-stu-id="59948-160">No</span></span> | <span data-ttu-id="59948-161">此功能已关闭。</span><span class="sxs-lookup"><span data-stu-id="59948-161">This feature is turned off.</span></span>  |  
| Browser Task Manager | <span data-ttu-id="59948-162">关闭</span><span class="sxs-lookup"><span data-stu-id="59948-162">Off</span></span> | <span data-ttu-id="59948-163">否</span><span class="sxs-lookup"><span data-stu-id="59948-163">No</span></span> | <span data-ttu-id="59948-164">此功能已关闭。</span><span class="sxs-lookup"><span data-stu-id="59948-164">This feature is turned off.</span></span>  |  
| Collections | <span data-ttu-id="59948-165">关闭</span><span class="sxs-lookup"><span data-stu-id="59948-165">Off</span></span> | <span data-ttu-id="59948-166">否</span><span class="sxs-lookup"><span data-stu-id="59948-166">No</span></span> | <span data-ttu-id="59948-167">此功能已关闭。</span><span class="sxs-lookup"><span data-stu-id="59948-167">This feature is turned off.</span></span>  |  
| Continue-where-I-left-off prompt | <span data-ttu-id="59948-168">关闭</span><span class="sxs-lookup"><span data-stu-id="59948-168">Off</span></span> | <span data-ttu-id="59948-169">否</span><span class="sxs-lookup"><span data-stu-id="59948-169">No</span></span> | <span data-ttu-id="59948-170">此功能已关闭。</span><span class="sxs-lookup"><span data-stu-id="59948-170">This feature is turned off.</span></span>  |  
| Downloads | <span data-ttu-id="59948-171">开</span><span class="sxs-lookup"><span data-stu-id="59948-171">On</span></span> | <span data-ttu-id="59948-172">是</span><span class="sxs-lookup"><span data-stu-id="59948-172">Yes</span></span> | <span data-ttu-id="59948-173">WebView2 提供了一个 API，允许你自定义下载 UI 以操作下载。</span><span class="sxs-lookup"><span data-stu-id="59948-173">WebView2 provides an API that allows you to customize the download UI to manipulate downloads.</span></span> <span data-ttu-id="59948-174">例如，可以阻止、重定向、保存、暂停等。</span><span class="sxs-lookup"><span data-stu-id="59948-174">For example, you can block, redirect, save, pause, and so on.</span></span>  <!--For more information, navigate to [download API][Webview2ReferenceDownloadApi].--> |  
| Edge Shopping | <span data-ttu-id="59948-175">关闭</span><span class="sxs-lookup"><span data-stu-id="59948-175">Off</span></span> | <span data-ttu-id="59948-176">否</span><span class="sxs-lookup"><span data-stu-id="59948-176">No</span></span> | <span data-ttu-id="59948-177">此功能已关闭。</span><span class="sxs-lookup"><span data-stu-id="59948-177">This feature is turned off.</span></span>  |  
| Family Safety | <span data-ttu-id="59948-178">关闭</span><span class="sxs-lookup"><span data-stu-id="59948-178">Off</span></span> | <span data-ttu-id="59948-179">否</span><span class="sxs-lookup"><span data-stu-id="59948-179">No</span></span> | <span data-ttu-id="59948-180">此功能已关闭。</span><span class="sxs-lookup"><span data-stu-id="59948-180">This feature is turned off.</span></span>  |  
| Favorites | <span data-ttu-id="59948-181">关闭</span><span class="sxs-lookup"><span data-stu-id="59948-181">Off</span></span> | <span data-ttu-id="59948-182">否</span><span class="sxs-lookup"><span data-stu-id="59948-182">No</span></span> | <span data-ttu-id="59948-183">此功能已关闭。</span><span class="sxs-lookup"><span data-stu-id="59948-183">This feature is turned off.</span></span>  |  
| IE Mode | <span data-ttu-id="59948-184">关闭</span><span class="sxs-lookup"><span data-stu-id="59948-184">Off</span></span> | <span data-ttu-id="59948-185">否</span><span class="sxs-lookup"><span data-stu-id="59948-185">No</span></span> | <span data-ttu-id="59948-186">此功能已关闭。</span><span class="sxs-lookup"><span data-stu-id="59948-186">This feature is turned off.</span></span> <span data-ttu-id="59948-187">与 IE 模式（如 MHT 或 BIN 支持）相比，WebView2 不支持 IE 模式 (行为) 。</span><span class="sxs-lookup"><span data-stu-id="59948-187">WebView2 doesn't support IE mode and has differences in behavior compared to IE (such as MHT or BIN support).</span></span> |  
| Immersive Reader | <span data-ttu-id="59948-188">关闭</span><span class="sxs-lookup"><span data-stu-id="59948-188">Off</span></span> | <span data-ttu-id="59948-189">否</span><span class="sxs-lookup"><span data-stu-id="59948-189">No</span></span> | <span data-ttu-id="59948-190">此功能取决于用于交互的浏览器 UI。</span><span class="sxs-lookup"><span data-stu-id="59948-190">This feature depends on the browser UI for interaction.</span></span>  <span data-ttu-id="59948-191">此功能已关闭。</span><span class="sxs-lookup"><span data-stu-id="59948-191">This feature is turned off.</span></span>  |  
| Intrusive Ads | <span data-ttu-id="59948-192">关闭</span><span class="sxs-lookup"><span data-stu-id="59948-192">Off</span></span> | <span data-ttu-id="59948-193">否</span><span class="sxs-lookup"><span data-stu-id="59948-193">No</span></span> | <span data-ttu-id="59948-194">此功能已关闭。</span><span class="sxs-lookup"><span data-stu-id="59948-194">This feature is turned off.</span></span>  |  
| <span data-ttu-id="59948-195">键盘快捷方式</span><span class="sxs-lookup"><span data-stu-id="59948-195">Keyboard shortcuts</span></span> | <span data-ttu-id="59948-196">查看详细信息</span><span class="sxs-lookup"><span data-stu-id="59948-196">Review Details</span></span> | <span data-ttu-id="59948-197">查看详细信息</span><span class="sxs-lookup"><span data-stu-id="59948-197">Review Details</span></span> | <span data-ttu-id="59948-198">默认情况下关闭的键盘快捷方式在 WebView2 中没有意义或导致问题。</span><span class="sxs-lookup"><span data-stu-id="59948-198">The keyboard shortcuts that are turned off by default either don't make sense or cause problems in WebView2.</span></span>  <span data-ttu-id="59948-199">不得打开或关闭这些快捷方式。</span><span class="sxs-lookup"><span data-stu-id="59948-199">You may not turn on or off these shortcuts.</span></span>  <span data-ttu-id="59948-200">相反，您可以使用 事件侦听组合键 `AcceleratorKeyPressed` ，并根据需要创建自定义响应。</span><span class="sxs-lookup"><span data-stu-id="59948-200">Instead, you may listen for a key combination using the `AcceleratorKeyPressed` event and create a custom response if needed.</span></span>  <span data-ttu-id="59948-201">有关详细信息，请导航到"[其他键盘快捷方式信息"。](#additional-keyboard-shortcuts-information)</span><span class="sxs-lookup"><span data-stu-id="59948-201">For more information, navigate to [Additional keyboard shortcuts information](#additional-keyboard-shortcuts-information).</span></span> |  
| <span data-ttu-id="59948-202">推送通知</span><span class="sxs-lookup"><span data-stu-id="59948-202">Push notifications</span></span> | <span data-ttu-id="59948-203">关闭</span><span class="sxs-lookup"><span data-stu-id="59948-203">Off</span></span> | <span data-ttu-id="59948-204">否</span><span class="sxs-lookup"><span data-stu-id="59948-204">No</span></span> | <span data-ttu-id="59948-205">WebView2 中未实现此功能。</span><span class="sxs-lookup"><span data-stu-id="59948-205">This feature is not implemented in WebView2.</span></span>  <span data-ttu-id="59948-206">有关详细信息，请导航到添加对[HTML5 通知 API (#308) 。 ][GithubMicrosoftedgeWebview2feedbackIssues308]</span><span class="sxs-lookup"><span data-stu-id="59948-206">For more information, navigate to [Add support for HTML5 Notification API (#308)][GithubMicrosoftedgeWebview2feedbackIssues308].</span></span> |  
| Read Aloud | <span data-ttu-id="59948-207">关闭</span><span class="sxs-lookup"><span data-stu-id="59948-207">Off</span></span> | <span data-ttu-id="59948-208">否</span><span class="sxs-lookup"><span data-stu-id="59948-208">No</span></span> | <span data-ttu-id="59948-209">此功能已关闭。</span><span class="sxs-lookup"><span data-stu-id="59948-209">This feature is turned off.</span></span>  |  
| Smart Screen | <span data-ttu-id="59948-210">开</span><span class="sxs-lookup"><span data-stu-id="59948-210">On</span></span>`*` | <span data-ttu-id="59948-211">否</span><span class="sxs-lookup"><span data-stu-id="59948-211">No</span></span> | `*` <span data-ttu-id="59948-212">此功能的 UI 已删除，但基础功能仍然可用。</span><span class="sxs-lookup"><span data-stu-id="59948-212">The UI for this feature has been removed, however the underlying functionality is still available.</span></span>  <span data-ttu-id="59948-213">此外，您还可以关闭 Smart Screen 使用命令行开关。</span><span class="sxs-lookup"><span data-stu-id="59948-213">Additionally, you may turn off Smart Screen using a command-line switch.</span></span>  |  
| Translate | <span data-ttu-id="59948-214">关闭</span><span class="sxs-lookup"><span data-stu-id="59948-214">Off</span></span> | <span data-ttu-id="59948-215">否</span><span class="sxs-lookup"><span data-stu-id="59948-215">No</span></span> | <span data-ttu-id="59948-216">此功能已关闭。</span><span class="sxs-lookup"><span data-stu-id="59948-216">This feature is turned off.</span></span>  |  
| Tracking Prevention | <span data-ttu-id="59948-217">开</span><span class="sxs-lookup"><span data-stu-id="59948-217">On</span></span>`*` | <span data-ttu-id="59948-218">否</span><span class="sxs-lookup"><span data-stu-id="59948-218">No</span></span> | `*` <span data-ttu-id="59948-219">此功能的 UI 已删除，但基础功能仍然可用。</span><span class="sxs-lookup"><span data-stu-id="59948-219">The UI for this feature has been removed, however the underlying functionality is still available.</span></span>  <span data-ttu-id="59948-220">跟踪防护始终设置为平衡。</span><span class="sxs-lookup"><span data-stu-id="59948-220">Tracking prevention is always set to balanced.</span></span>|  
| Profile and Identity | <span data-ttu-id="59948-221">关闭</span><span class="sxs-lookup"><span data-stu-id="59948-221">Off</span></span> | <span data-ttu-id="59948-222">否</span><span class="sxs-lookup"><span data-stu-id="59948-222">No</span></span> | <span data-ttu-id="59948-223">同步收藏夹、Cookie 等的功能已关闭。</span><span class="sxs-lookup"><span data-stu-id="59948-223">The feature that syncs your favorites, cookies, and so on, is turned off.</span></span>  |  
| Web Payment API | <span data-ttu-id="59948-224">关闭</span><span class="sxs-lookup"><span data-stu-id="59948-224">Off</span></span> | <span data-ttu-id="59948-225">否</span><span class="sxs-lookup"><span data-stu-id="59948-225">No</span></span> | <span data-ttu-id="59948-226">此功能已关闭。</span><span class="sxs-lookup"><span data-stu-id="59948-226">This feature is turned off.</span></span>  | 
| Windows Defender Application Guard | <span data-ttu-id="59948-227">关闭</span><span class="sxs-lookup"><span data-stu-id="59948-227">Off</span></span> | <span data-ttu-id="59948-228">否</span><span class="sxs-lookup"><span data-stu-id="59948-228">No</span></span> | <span data-ttu-id="59948-229">此功能已关闭。</span><span class="sxs-lookup"><span data-stu-id="59948-229">This feature is turned off.</span></span>  |  
| edge:// URLs | <span data-ttu-id="59948-230">查看详细信息</span><span class="sxs-lookup"><span data-stu-id="59948-230">Review Details</span></span> | <span data-ttu-id="59948-231">否</span><span class="sxs-lookup"><span data-stu-id="59948-231">No</span></span> | <span data-ttu-id="59948-232">设置浏览器Microsoft Edge URL `edge://` 上。</span><span class="sxs-lookup"><span data-stu-id="59948-232">Settings for the Microsoft Edge browser are on `edge://` URLs.</span></span>  <span data-ttu-id="59948-233">由于这些网页中的大多数Microsoft Edge WebView2 上下文中具有品牌或没有意义，因此其中一些 URL 已关闭。</span><span class="sxs-lookup"><span data-stu-id="59948-233">Because most of these webpages have Microsoft Edge branding or don't make sense within the context of WebView2, some of these URLs are turned off.</span></span>  <span data-ttu-id="59948-234">有关详细信息，请导航到["阻止的内部 URL"。](#blocked-internal-urls)</span><span class="sxs-lookup"><span data-stu-id="59948-234">For more information, navigate to [Blocked internal URLs](#blocked-internal-urls).</span></span>  |  

## <a name="blocked-internal-urls"></a><span data-ttu-id="59948-235">阻止的内部 URL</span><span class="sxs-lookup"><span data-stu-id="59948-235">Blocked internal URLs</span></span>  

<span data-ttu-id="59948-236">以下Microsoft Edge和 Google Chrome 设置网页在 WebView2 中不可用。</span><span class="sxs-lookup"><span data-stu-id="59948-236">The following Microsoft Edge and Google Chrome settings webpages aren't available in WebView2.</span></span>  

*   `chrome-search://local-ntp/local-ntp.html`  
*   `edge://application-guard-internals`  
*   `edge://apps`  
*   `edge://compat`  
*   `edge://extensions`  
*   `edge://favorites`  
*   `edge://help`  
*   `edge://management`  
*   `edge://network-error`  
*   `edge://new-tab-page`  
*   `edge://newtab`  
*   `edge://omnibox`  
*   `edge://settings`  
*   `edge://supervised-user-internals`  
*   `edge://version`  
    
## <a name="additional-keyboard-shortcuts-information"></a><span data-ttu-id="59948-237">其他键盘快捷方式信息</span><span class="sxs-lookup"><span data-stu-id="59948-237">Additional keyboard shortcuts information</span></span>  

<span data-ttu-id="59948-238">键盘快捷方式或键绑定在 Microsoft Edge 和 WebView2 中受支持。</span><span class="sxs-lookup"><span data-stu-id="59948-238">Keyboard shortcuts or key bindings are supported in Microsoft Edge and WebView2.</span></span>  <span data-ttu-id="59948-239">当Microsoft Edge时，默认键绑定可能会更改。</span><span class="sxs-lookup"><span data-stu-id="59948-239">When Microsoft Edge updates, the default key bindings may change.</span></span>  <span data-ttu-id="59948-240">此外，如果 WebView2 现在支持此功能，则默认情况下关闭的键盘快捷方式可能会打开。</span><span class="sxs-lookup"><span data-stu-id="59948-240">Furthermore, a keyboard shortcut that is turned off by default may turn on if the feature is now supported in WebView2.</span></span>  <span data-ttu-id="59948-241">若要避免更改键盘快捷方式，可以设置为 ，这将关闭访问浏览器功能的所有键，但会启用所有基本的文本编辑和移动 `AreBrowserAcceleratorKeysEnabled` `FALSE` 快捷方式。</span><span class="sxs-lookup"><span data-stu-id="59948-241">To avoid changes to your keyboard shortcuts, you may set `AreBrowserAcceleratorKeysEnabled` to `FALSE`, which turns off all keys that access browser features, but keeps all basic text-editing and movement shortcuts turned on.</span></span>  

<span data-ttu-id="59948-242">下表列出了 WebView2 中始终关闭的快捷方式。</span><span class="sxs-lookup"><span data-stu-id="59948-242">The following table lists the shortcuts that are always turned off in WebView2.</span></span>  <span data-ttu-id="59948-243">星号 \ (\) 字符指示快捷方式未关闭，但它访问的功能已关闭或不适用于 `*` WebView2。</span><span class="sxs-lookup"><span data-stu-id="59948-243">An asterisk \(`*`\) character indicates that the shortcut isn't turned off, but the feature it accesses is turned off or doesn't apply to WebView2.</span></span>  

| <span data-ttu-id="59948-244">操作</span><span class="sxs-lookup"><span data-stu-id="59948-244">Action</span></span> | <span data-ttu-id="59948-245">Windows</span><span class="sxs-lookup"><span data-stu-id="59948-245">Windows</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="59948-246">添加到</span><span class="sxs-lookup"><span data-stu-id="59948-246">Add to</span></span> Favorites | `Ctrl`+`D` |  
| <span data-ttu-id="59948-247">将所有选项卡添加到</span><span class="sxs-lookup"><span data-stu-id="59948-247">Add All Tabs to</span></span> Favorites | `Ctrl`+`Shift`+`D` |  
| <span data-ttu-id="59948-248">焦点位置</span><span class="sxs-lookup"><span data-stu-id="59948-248">Focus Location</span></span> | `Ctrl`+`L, Alt`+`D` |  
| <span data-ttu-id="59948-249">粘贴并转到</span><span class="sxs-lookup"><span data-stu-id="59948-249">Paste and Go</span></span> | `Ctrl`+`Shift`+`L` |  
| <span data-ttu-id="59948-250">打开文件</span><span class="sxs-lookup"><span data-stu-id="59948-250">Open File</span></span> | `Ctrl`+`O` |  
| Read Aloud `*` | `Ctrl`+`Shift`+`U` |  
| <span data-ttu-id="59948-251">Web 捕获</span><span class="sxs-lookup"><span data-stu-id="59948-251">Web Capture</span></span> `*` | `Ctrl`+`Shift`+`S` |  
| <span data-ttu-id="59948-252">边栏</span><span class="sxs-lookup"><span data-stu-id="59948-252">Sidebar</span></span> `*` | `Ctrl`+`Shift`+`E` |  
| <span data-ttu-id="59948-253">保存页面</span><span class="sxs-lookup"><span data-stu-id="59948-253">Save Page</span></span> | `Ctrl`+`S` |  
| <span data-ttu-id="59948-254">选择最后一个选项卡</span><span class="sxs-lookup"><span data-stu-id="59948-254">Select Last Tab</span></span> | `Ctrl`+`9` |  
| <span data-ttu-id="59948-255">选择下一个选项卡</span><span class="sxs-lookup"><span data-stu-id="59948-255">Select Next Tab</span></span> | `Ctrl`+`Tab` |  
| <span data-ttu-id="59948-256">选择上一个选项卡</span><span class="sxs-lookup"><span data-stu-id="59948-256">Select Previous Tab</span></span> | `Ctrl`+`Shift`+`Tab` |  
| <span data-ttu-id="59948-257">选择选项卡 \ (1 - 8\) </span><span class="sxs-lookup"><span data-stu-id="59948-257">Select Tab \(1 - 8\)</span></span> | `Ctrl`+`(1-8)` |  
| <span data-ttu-id="59948-258">显示 Favorites 栏</span><span class="sxs-lookup"><span data-stu-id="59948-258">Show Favorites Bar</span></span> `*` | `Ctrl`+`Shift`+`B` |  
| <span data-ttu-id="59948-259">帮助</span><span class="sxs-lookup"><span data-stu-id="59948-259">Help</span></span> | `F1` |  
| <span data-ttu-id="59948-260">焦点下一个窗格</span><span class="sxs-lookup"><span data-stu-id="59948-260">Focus Next Pane</span></span> `*` | `F6` |  
| <span data-ttu-id="59948-261">焦点上一个窗格</span><span class="sxs-lookup"><span data-stu-id="59948-261">Focus Previous Pane</span></span> `*` | `Shift`+`F6` |  
| <span data-ttu-id="59948-262">项目浏览</span><span class="sxs-lookup"><span data-stu-id="59948-262">Caret Browsing</span></span> `*` | `F7` |  
| <span data-ttu-id="59948-263">阅读视图</span><span class="sxs-lookup"><span data-stu-id="59948-263">Reading View</span></span> `*` | `F9` |  
| <span data-ttu-id="59948-264">焦点菜单栏</span><span class="sxs-lookup"><span data-stu-id="59948-264">Focus Menu Bar</span></span> | `F10` |  
| <span data-ttu-id="59948-265">显示标识菜单</span><span class="sxs-lookup"><span data-stu-id="59948-265">Show Identity Menu</span></span> `*` | `Ctrl`+`Shift`+`M` |  
| Browser Task Manager `*` | `Shift`+`Escape` |  
| <span data-ttu-id="59948-266">Edge 反馈</span><span class="sxs-lookup"><span data-stu-id="59948-266">Edge Feedback</span></span> `*` | `Shift`+`Alt`+`I` |  
| <span data-ttu-id="59948-267">静音选项卡</span><span class="sxs-lookup"><span data-stu-id="59948-267">Mute Tab</span></span> `*` | `Ctrl`+`M` |  
| <span data-ttu-id="59948-268">新建隐身窗口</span><span class="sxs-lookup"><span data-stu-id="59948-268">New Incognito Window</span></span> | `Ctrl`+`Shift`+`N` |  
| <span data-ttu-id="59948-269">新建选项卡</span><span class="sxs-lookup"><span data-stu-id="59948-269">New Tab</span></span> | `Ctrl`+`T` |  
| <span data-ttu-id="59948-270">新建窗口</span><span class="sxs-lookup"><span data-stu-id="59948-270">New Window</span></span> | `Ctrl`+`N` |  
| <span data-ttu-id="59948-271">"还原上次关闭"选项卡</span><span class="sxs-lookup"><span data-stu-id="59948-271">Restore Last Closed Tab</span></span> | `Ctrl`+`Shift`+`T` |  
| <span data-ttu-id="59948-272">对焦</span><span class="sxs-lookup"><span data-stu-id="59948-272">Focus</span></span> Favorites | `Alt`+`Shift`+`B` |  
| <span data-ttu-id="59948-273">焦点非活动弹出窗口</span><span class="sxs-lookup"><span data-stu-id="59948-273">Focus Inactive Popup</span></span> | `Alt`+`Shift`+`A` |  
| <span data-ttu-id="59948-274">焦点搜索</span><span class="sxs-lookup"><span data-stu-id="59948-274">Focus Search</span></span> | `Ctrl`<span data-ttu-id="59948-275">+`E`, `Ctrl`+`K`,</span><span class="sxs-lookup"><span data-stu-id="59948-275">+`E`, `Ctrl`+`K`,</span></span> `Search Key` |  
| <span data-ttu-id="59948-276">"重复"选项卡</span><span class="sxs-lookup"><span data-stu-id="59948-276">Duplicate Tab</span></span> | `Ctrl`+`Shift`+`K` |  
| <span data-ttu-id="59948-277">焦点工具栏</span><span class="sxs-lookup"><span data-stu-id="59948-277">Focus Toolbar</span></span> `*` | `Alt`+`Shift`+`T` |  
| <span data-ttu-id="59948-278">主页</span><span class="sxs-lookup"><span data-stu-id="59948-278">Home</span></span> | `Alt`<span data-ttu-id="59948-279">+`Home`,</span><span class="sxs-lookup"><span data-stu-id="59948-279">+`Home`,</span></span> `Browser Home Key` |  
| <span data-ttu-id="59948-280">显示应用菜单</span><span class="sxs-lookup"><span data-stu-id="59948-280">Show App Menu</span></span> | `Alt`+`E, Alt`+`F` |  
| <span data-ttu-id="59948-281">显示</span><span class="sxs-lookup"><span data-stu-id="59948-281">Show</span></span> Favorites | `Ctrl`+`Shift`+`O` |  
| <span data-ttu-id="59948-282">显示</span><span class="sxs-lookup"><span data-stu-id="59948-282">Show</span></span> Downloads | `Ctrl`+`J` |  
| <span data-ttu-id="59948-283">显示历史记录</span><span class="sxs-lookup"><span data-stu-id="59948-283">Show History</span></span> | `Ctrl`+`H` |  
| <span data-ttu-id="59948-284">显示阅读模式栏</span><span class="sxs-lookup"><span data-stu-id="59948-284">Show Reading Mode Bar</span></span> `*` | `Shift`+`Alt`+`R` |  
| <span data-ttu-id="59948-285">显示</span><span class="sxs-lookup"><span data-stu-id="59948-285">Show</span></span> Collections `*` | `Ctrl`+`Shift`+`Y` |  

<span data-ttu-id="59948-286">以下键盘快捷方式始终关闭，在未处理事件时显示的窗口中 `NewWindowRequested` 除外。</span><span class="sxs-lookup"><span data-stu-id="59948-286">The following keyboard shortcuts are always turned off, except in windows that display when the `NewWindowRequested` event isn't handled.</span></span>

| <span data-ttu-id="59948-287">操作</span><span class="sxs-lookup"><span data-stu-id="59948-287">Action</span></span> | <span data-ttu-id="59948-288">Windows</span><span class="sxs-lookup"><span data-stu-id="59948-288">Windows</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="59948-289">关闭选项卡</span><span class="sxs-lookup"><span data-stu-id="59948-289">Close Tab</span></span> | `Ctrl`+`W, Ctrl`+`F4` |  
| <span data-ttu-id="59948-290">关闭窗口</span><span class="sxs-lookup"><span data-stu-id="59948-290">Close Window</span></span> | `Ctrl`+`Shift`+`W` |  
| <span data-ttu-id="59948-291">全屏</span><span class="sxs-lookup"><span data-stu-id="59948-291">Fullscreen</span></span> | `F11` |  

<span data-ttu-id="59948-292">如果设置为 `AreBrowserAcceleratorKeysEnabled` `FALSE` ，则以下其他键盘快捷方式将关闭。</span><span class="sxs-lookup"><span data-stu-id="59948-292">If you set `AreBrowserAcceleratorKeysEnabled` to `FALSE`, the following additional keyboard shortcuts are turned off.</span></span>  

| <span data-ttu-id="59948-293">操作</span><span class="sxs-lookup"><span data-stu-id="59948-293">Action</span></span> | <span data-ttu-id="59948-294">Windows</span><span class="sxs-lookup"><span data-stu-id="59948-294">Windows</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="59948-295">停止</span><span class="sxs-lookup"><span data-stu-id="59948-295">Stop</span></span> | `Escape` |  
| <span data-ttu-id="59948-296">在页面上查找</span><span class="sxs-lookup"><span data-stu-id="59948-296">Find on Page</span></span> | `Ctrl`+`F` |  
| <span data-ttu-id="59948-297">查找下一个</span><span class="sxs-lookup"><span data-stu-id="59948-297">Find Next</span></span> | `Ctrl`+`G` |  
| <span data-ttu-id="59948-298">查找上一个</span><span class="sxs-lookup"><span data-stu-id="59948-298">Find Previous</span></span> | `Ctrl`+`Shift`+`G` |  
| <span data-ttu-id="59948-299">Print</span><span class="sxs-lookup"><span data-stu-id="59948-299">Print</span></span> | `Ctrl`+`P` |  
| <span data-ttu-id="59948-300">刷新</span><span class="sxs-lookup"><span data-stu-id="59948-300">Refresh</span></span> | `Ctrl`<span data-ttu-id="59948-301">+`R`, `F5`,</span><span class="sxs-lookup"><span data-stu-id="59948-301">+`R`, `F5`,</span></span> `Reload Key` |  
| <span data-ttu-id="59948-302">刷新（不含缓存）</span><span class="sxs-lookup"><span data-stu-id="59948-302">Refresh Without Cache</span></span> | `Ctrl`<span data-ttu-id="59948-303">+`Shift`+`R`, `Ctrl`+`F5`, `Shift`+`F5`, `Ctrl`+`Refresh`, `Shift`+</span><span class="sxs-lookup"><span data-stu-id="59948-303">+`Shift`+`R`, `Ctrl`+`F5`, `Shift`+`F5`, `Ctrl`+`Refresh`, `Shift`+</span></span>`Refresh` |  
| <span data-ttu-id="59948-304">缩小</span><span class="sxs-lookup"><span data-stu-id="59948-304">Zoom Out</span></span> | `Ctrl`+`-` |  
| <span data-ttu-id="59948-305">放大</span><span class="sxs-lookup"><span data-stu-id="59948-305">Zoom In</span></span> | `Ctrl`+`+` |  
| <span data-ttu-id="59948-306">重置缩放</span><span class="sxs-lookup"><span data-stu-id="59948-306">Reset Zoom</span></span> | `Ctrl`+`0` |  
| <span data-ttu-id="59948-307">查找下一个</span><span class="sxs-lookup"><span data-stu-id="59948-307">Find Next</span></span> | `F3` |  
| <span data-ttu-id="59948-308">查找上一个</span><span class="sxs-lookup"><span data-stu-id="59948-308">Find Previous</span></span> | `Shift`+`F3` |  
| <span data-ttu-id="59948-309">后退</span><span class="sxs-lookup"><span data-stu-id="59948-309">Back</span></span> | `Alt`+`Left, Browser Back Key` |  
| <span data-ttu-id="59948-310">前进</span><span class="sxs-lookup"><span data-stu-id="59948-310">Forward</span></span> | `Alt`<span data-ttu-id="59948-311">+`Right`,</span><span class="sxs-lookup"><span data-stu-id="59948-311">+`Right`,</span></span> `Browser Forward Key` |  
| <span data-ttu-id="59948-312">Print</span><span class="sxs-lookup"><span data-stu-id="59948-312">Print</span></span> | `Ctrl`+`P` |  
| <span data-ttu-id="59948-313">打开/关闭 DevTools</span><span class="sxs-lookup"><span data-stu-id="59948-313">Open / Close DevTools</span></span> | `Ctrl`+`Shift`+`I` |  
| <span data-ttu-id="59948-314">打开 DevTools 控制台</span><span class="sxs-lookup"><span data-stu-id="59948-314">Open DevTools Console</span></span> | `Ctrl`+`Shift`+`J` |  
| <span data-ttu-id="59948-315">打开 DevTools Inspect</span><span class="sxs-lookup"><span data-stu-id="59948-315">Open DevTools Inspect</span></span> | `Ctrl`+`Shift`+`C` |  

> [!Note] 
> <span data-ttu-id="59948-316">若要单独自定义任何键，请使用 [AcceleratorKeyPressed][DotnetApiMicrosoftWebWebview2CoreCorewebview2controllerAcceleratorkeypressedViewWebview2Dotnet1077444] 事件。</span><span class="sxs-lookup"><span data-stu-id="59948-316">To customize any of the keys individually, use the [AcceleratorKeyPressed][DotnetApiMicrosoftWebWebview2CoreCorewebview2controllerAcceleratorkeypressedViewWebview2Dotnet1077444] event.</span></span>  

## <a name="getting-in-touch-with-the-microsoft-edge-webview2-team"></a><span data-ttu-id="59948-317">与 WebView2 Microsoft Edge联系</span><span class="sxs-lookup"><span data-stu-id="59948-317">Getting in touch with the Microsoft Edge WebView2 team</span></span>  

[!INCLUDE [contact WebView2 team note](../includes/contact-webview-team-note.md)]  

<!-- links -->  

<!--[Webview2ReferenceDownloadApi]: ./download-api.md "download API | Microsoft Docs"  -->  

[DotnetApiMicrosoftWebWebview2CoreCorewebview2controllerAcceleratorkeypressedViewWebview2Dotnet1077444]: /dotnet/api/microsoft.web.webview2.core.corewebview2controller.acceleratorkeypressed?view=webview2-dotnet-1.0.774.44&preserve-view=true "CoreWebView2Controller.AcceleratorKeyPressed 事件|Microsoft Docs"  

[DevtoolsShortcutsIndex]: ../../devtools-guide-chromium/shortcuts/index.md "Microsoft Edge DevTools 键盘快捷方式 | Microsoft Docs"  

[GithubMicrosoftedgeWebview2feedbackIssues308]: https://github.com/MicrosoftEdge/WebView2Feedback/issues/308 "添加对 HTML5 通知 API (#308) |GitHub"  

[PeterExperimentsChromiumCommandLineSwitches]: https://peter.sh/experiments/chromium-command-line-switches "命令行Chromium列表|Peter Beverloo"  
