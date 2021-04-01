---
<span data-ttu-id="332ce-101">description： Microsoft Edge 和 WebView2 标题之间的功能差异：Microsoft Edge 和 WebView2 之间的功能差异作者：MSEdgeTeam ms.author： msedgedevrel ms.date： 03/31/2021 ms.topic： conceptual ms.prod： microsoft-edge ms.technology： webview keywords： IWebView2， IWebView2WebView、WebView2、webview、wpf 应用、wpf、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、edge html no-loc：</span><span class="sxs-lookup"><span data-stu-id="332ce-101">description: Feature differences between Microsoft Edge and WebView2 title: Feature differences between Microsoft Edge and WebView2 author: MSEdgeTeam ms.author: msedgedevrel ms.date: 03/31/2021 ms.topic: conceptual ms.prod: microsoft-edge ms.technology: webview keywords: IWebView2, IWebView2WebView, WebView2, webview, wpf apps, wpf, edge, ICoreWebView2, ICoreWebView2Host, browser control, edge html no-loc:</span></span>
- <span data-ttu-id="332ce-102">"Autofill for Addresses"</span><span class="sxs-lookup"><span data-stu-id="332ce-102">"Autofill for Addresses"</span></span>
- <span data-ttu-id="332ce-103">"Autofill for Passwords"</span><span class="sxs-lookup"><span data-stu-id="332ce-103">"Autofill for Passwords"</span></span>
- <span data-ttu-id="332ce-104">"Autofill for Payments""</span><span class="sxs-lookup"><span data-stu-id="332ce-104">"Autofill for Payments""</span></span>
- <span data-ttu-id="332ce-105">"Browser Extensions""</span><span class="sxs-lookup"><span data-stu-id="332ce-105">"Browser Extensions""</span></span>
- <span data-ttu-id="332ce-106">"Browser Task Manager"</span><span class="sxs-lookup"><span data-stu-id="332ce-106">"Browser Task Manager"</span></span>
- <span data-ttu-id="332ce-107">"Collections"</span><span class="sxs-lookup"><span data-stu-id="332ce-107">"Collections"</span></span>
- <span data-ttu-id="332ce-108">"Continue-where-I-left-off prompt"</span><span class="sxs-lookup"><span data-stu-id="332ce-108">"Continue-where-I-left-off prompt"</span></span>
- <span data-ttu-id="332ce-109">"Downloads"</span><span class="sxs-lookup"><span data-stu-id="332ce-109">"Downloads"</span></span>
- <span data-ttu-id="332ce-110">"Edge Shopping"</span><span class="sxs-lookup"><span data-stu-id="332ce-110">"Edge Shopping"</span></span>
- <span data-ttu-id="332ce-111">"Family Safety"</span><span class="sxs-lookup"><span data-stu-id="332ce-111">"Family Safety"</span></span>
- <span data-ttu-id="332ce-112">"Favorites"</span><span class="sxs-lookup"><span data-stu-id="332ce-112">"Favorites"</span></span>
- <span data-ttu-id="332ce-113">"Hotkeys"</span><span class="sxs-lookup"><span data-stu-id="332ce-113">"Hotkeys"</span></span>
- <span data-ttu-id="332ce-114">"IE Mode"</span><span class="sxs-lookup"><span data-stu-id="332ce-114">"IE Mode"</span></span>
- <span data-ttu-id="332ce-115">"Immersive Reader"</span><span class="sxs-lookup"><span data-stu-id="332ce-115">"Immersive Reader"</span></span>
- <span data-ttu-id="332ce-116">"Intrusive Ads"</span><span class="sxs-lookup"><span data-stu-id="332ce-116">"Intrusive Ads"</span></span>
- <span data-ttu-id="332ce-117">"Read Aloud"</span><span class="sxs-lookup"><span data-stu-id="332ce-117">"Read Aloud"</span></span>
- <span data-ttu-id="332ce-118">"Smart Screen"</span><span class="sxs-lookup"><span data-stu-id="332ce-118">"Smart Screen"</span></span>
- <span data-ttu-id="332ce-119">"Translate"</span><span class="sxs-lookup"><span data-stu-id="332ce-119">"Translate"</span></span>
- <span data-ttu-id="332ce-120">"Tracking Prevention"</span><span class="sxs-lookup"><span data-stu-id="332ce-120">"Tracking Prevention"</span></span>
- <span data-ttu-id="332ce-121">"Profile and Identity"</span><span class="sxs-lookup"><span data-stu-id="332ce-121">"Profile and Identity"</span></span>
- <span data-ttu-id="332ce-122">"Web Payment API"</span><span class="sxs-lookup"><span data-stu-id="332ce-122">"Web Payment API"</span></span>
- <span data-ttu-id="332ce-123">"Windows Defender Application Guard"</span><span class="sxs-lookup"><span data-stu-id="332ce-123">"Windows Defender Application Guard"</span></span>
- <span data-ttu-id="332ce-124">"edge:// URLs"</span><span class="sxs-lookup"><span data-stu-id="332ce-124">"edge:// URLs"</span></span>

---
# <a name="browser-feature-differences-between-microsoft-edge-and-webview2"></a><span data-ttu-id="332ce-125">Microsoft Edge 和 WebView2 之间的浏览器功能差异</span><span class="sxs-lookup"><span data-stu-id="332ce-125">Browser feature differences between Microsoft Edge and WebView2</span></span>  

<span data-ttu-id="332ce-126">WebView2 基于新的 Microsoft Edge 浏览器。</span><span class="sxs-lookup"><span data-stu-id="332ce-126">WebView2 is based on the new Microsoft Edge browser.</span></span>  <span data-ttu-id="332ce-127">你有机会将功能从浏览器扩展到基于 WebView2 的应用，这很有用。</span><span class="sxs-lookup"><span data-stu-id="332ce-127">You have the opportunity to extend features from the browser to WebView2-based apps, which is useful.</span></span>  <span data-ttu-id="332ce-128">但是，由于 WebView2 不限于类似浏览器的应用，因此需要修改或删除一些浏览器功能。</span><span class="sxs-lookup"><span data-stu-id="332ce-128">However, since WebView2 isn't limited to browser-like apps, there are some browser features that need to be modified or removed.</span></span>   <span data-ttu-id="332ce-129">本文提供以下信息。</span><span class="sxs-lookup"><span data-stu-id="332ce-129">This article provides the following information.</span></span>  

*   <span data-ttu-id="332ce-130">修改后的浏览器功能和支持信息。</span><span class="sxs-lookup"><span data-stu-id="332ce-130">The modified browser features and supporting information.</span></span>   
*   <span data-ttu-id="332ce-131">启用或关闭功能的功能。</span><span class="sxs-lookup"><span data-stu-id="332ce-131">The ability to turn on or off the feature.</span></span>  
*   <span data-ttu-id="332ce-132">有关键盘快捷方式的指南。</span><span class="sxs-lookup"><span data-stu-id="332ce-132">Guidance on keyboard shortcuts.</span></span>  
    
## <a name="design-guidelines"></a><span data-ttu-id="332ce-133">设计指南</span><span class="sxs-lookup"><span data-stu-id="332ce-133">Design guidelines</span></span>  

<span data-ttu-id="332ce-134">在 WebView2 上下文中，浏览器功能遵循以下设计准则。</span><span class="sxs-lookup"><span data-stu-id="332ce-134">In the context of WebView2, browser features adhere to the following design guidelines.</span></span>  

*   <span data-ttu-id="332ce-135">大多数功能在 WebView2 和 Microsoft Edge 中都相同。</span><span class="sxs-lookup"><span data-stu-id="332ce-135">Most features work the same in WebView2 and Microsoft Edge.</span></span>  <span data-ttu-id="332ce-136">如果功能在 WebView2 上下文中不起作用或出于其他原因，则功能会修改或关闭。</span><span class="sxs-lookup"><span data-stu-id="332ce-136">If a feature doesn't make sense in the context of WebView2 or for other reasons, the feature is modified or turned off.</span></span> 
*   <span data-ttu-id="332ce-137">WebView2 功能不包括 Microsoft Edge 品牌。</span><span class="sxs-lookup"><span data-stu-id="332ce-137">WebView2 features don't include Microsoft Edge branding.</span></span>  
    
## <a name="features"></a><span data-ttu-id="332ce-138">功能</span><span class="sxs-lookup"><span data-stu-id="332ce-138">Features</span></span>  

<span data-ttu-id="332ce-139">下表显示了与 Microsoft Edge 浏览器不同的 WebView2 功能。</span><span class="sxs-lookup"><span data-stu-id="332ce-139">The following table displays the WebView2 features that differ from the Microsoft Edge browser.</span></span>   

*   <span data-ttu-id="332ce-140">**默认** 状态指示功能是新 WebView2 实例上默认体验的一部分。</span><span class="sxs-lookup"><span data-stu-id="332ce-140">**Default state** indicates that the feature is part of the default experience on a new WebView2 instance.</span></span>  
*   <span data-ttu-id="332ce-141">**可** 配置指示可以使用 WebView2 API 或命令行开关打开或关闭该功能。</span><span class="sxs-lookup"><span data-stu-id="332ce-141">**Configurable** indicates that you may turn on or off the feature using WebView2 APIs or command-line switches.</span></span>  
    
> [!NOTE]  
> <span data-ttu-id="332ce-142">本文不介绍使用命令行开关修改功能。</span><span class="sxs-lookup"><span data-stu-id="332ce-142">This article doesn't cover modifying features using command-line switches.</span></span>  <span data-ttu-id="332ce-143">有关使用命令行开关打开和关闭功能的信息，请导航到 [Chromium 命令行开关的列表][PeterExperimentsChromiumCommandLineSwitches]。</span><span class="sxs-lookup"><span data-stu-id="332ce-143">For more information about turning on and off features with command-line switches, navigate to [List of Chromium Command Line Switches][PeterExperimentsChromiumCommandLineSwitches].</span></span>  
    
| <span data-ttu-id="332ce-144">功能</span><span class="sxs-lookup"><span data-stu-id="332ce-144">Feature</span></span> | <span data-ttu-id="332ce-145">默认状态</span><span class="sxs-lookup"><span data-stu-id="332ce-145">Default state</span></span> | <span data-ttu-id="332ce-146">可配置</span><span class="sxs-lookup"><span data-stu-id="332ce-146">Configurable</span></span> | <span data-ttu-id="332ce-147">详细信息</span><span class="sxs-lookup"><span data-stu-id="332ce-147">Details</span></span> |  
|:--- |:--- |:--- | :--- |  
| Autofill for Addresses | <span data-ttu-id="332ce-148">开</span><span class="sxs-lookup"><span data-stu-id="332ce-148">On</span></span> | <span data-ttu-id="332ce-149">是</span><span class="sxs-lookup"><span data-stu-id="332ce-149">Yes</span></span> | <span data-ttu-id="332ce-150">默认情况下，此功能已打开，可以使用 WebView2 自动填充 API 将其打开或关闭。</span><span class="sxs-lookup"><span data-stu-id="332ce-150">This feature is turned on by default, you may turn it on or off using WebView2 Autofill APIs.</span></span>  |  
| Autofill for Passwords | <span data-ttu-id="332ce-151">开</span><span class="sxs-lookup"><span data-stu-id="332ce-151">On</span></span> | <span data-ttu-id="332ce-152">是</span><span class="sxs-lookup"><span data-stu-id="332ce-152">Yes</span></span> | <span data-ttu-id="332ce-153">默认情况下，此功能已打开，可以使用 WebView2 自动填充 API 将其打开或关闭。</span><span class="sxs-lookup"><span data-stu-id="332ce-153">This feature is turned on by default, you may turn it on or off using WebView2 Autofill APIs.</span></span>  |  
| <span data-ttu-id="332ce-154">付款自动填充</span><span class="sxs-lookup"><span data-stu-id="332ce-154">Autofill for Payments</span></span> | <span data-ttu-id="332ce-155">关闭</span><span class="sxs-lookup"><span data-stu-id="332ce-155">Off</span></span> | <span data-ttu-id="332ce-156">否</span><span class="sxs-lookup"><span data-stu-id="332ce-156">No</span></span> | <span data-ttu-id="332ce-157">此功能已关闭。</span><span class="sxs-lookup"><span data-stu-id="332ce-157">This feature is turned off.</span></span>  |  
| <span data-ttu-id="332ce-158">浏览器扩展</span><span class="sxs-lookup"><span data-stu-id="332ce-158">Browser Extensions</span></span> | <span data-ttu-id="332ce-159">关闭</span><span class="sxs-lookup"><span data-stu-id="332ce-159">Off</span></span> | <span data-ttu-id="332ce-160">否</span><span class="sxs-lookup"><span data-stu-id="332ce-160">No</span></span> | <span data-ttu-id="332ce-161">此功能已关闭。</span><span class="sxs-lookup"><span data-stu-id="332ce-161">This feature is turned off.</span></span>  |  
| Browser Task Manager | <span data-ttu-id="332ce-162">关闭</span><span class="sxs-lookup"><span data-stu-id="332ce-162">Off</span></span> | <span data-ttu-id="332ce-163">否</span><span class="sxs-lookup"><span data-stu-id="332ce-163">No</span></span> | <span data-ttu-id="332ce-164">此功能已关闭。</span><span class="sxs-lookup"><span data-stu-id="332ce-164">This feature is turned off.</span></span>  |  
| Collections | <span data-ttu-id="332ce-165">关闭</span><span class="sxs-lookup"><span data-stu-id="332ce-165">Off</span></span> | <span data-ttu-id="332ce-166">否</span><span class="sxs-lookup"><span data-stu-id="332ce-166">No</span></span> | <span data-ttu-id="332ce-167">此功能已关闭。</span><span class="sxs-lookup"><span data-stu-id="332ce-167">This feature is turned off.</span></span>  |  
| Continue-where-I-left-off prompt | <span data-ttu-id="332ce-168">关闭</span><span class="sxs-lookup"><span data-stu-id="332ce-168">Off</span></span> | <span data-ttu-id="332ce-169">否</span><span class="sxs-lookup"><span data-stu-id="332ce-169">No</span></span> | <span data-ttu-id="332ce-170">此功能已关闭。</span><span class="sxs-lookup"><span data-stu-id="332ce-170">This feature is turned off.</span></span>  |  
| Downloads | <span data-ttu-id="332ce-171">开</span><span class="sxs-lookup"><span data-stu-id="332ce-171">On</span></span> | <span data-ttu-id="332ce-172">是</span><span class="sxs-lookup"><span data-stu-id="332ce-172">Yes</span></span> | <span data-ttu-id="332ce-173">WebView2 提供了一个 API，允许你自定义下载 UI 以操作下载。</span><span class="sxs-lookup"><span data-stu-id="332ce-173">WebView2 provides an API that allows you to customize the download UI to manipulate downloads.</span></span> <span data-ttu-id="332ce-174">例如，可以阻止、重定向、保存、暂停等。</span><span class="sxs-lookup"><span data-stu-id="332ce-174">For example, you can block, redirect, save, pause, and so on.</span></span>  <!--For more information, navigate to [download API][Webview2ReferenceDownloadApi].--> |  
| Edge Shopping | <span data-ttu-id="332ce-175">关闭</span><span class="sxs-lookup"><span data-stu-id="332ce-175">Off</span></span> | <span data-ttu-id="332ce-176">否</span><span class="sxs-lookup"><span data-stu-id="332ce-176">No</span></span> | <span data-ttu-id="332ce-177">此功能已关闭。</span><span class="sxs-lookup"><span data-stu-id="332ce-177">This feature is turned off.</span></span>  |  
| Family Safety | <span data-ttu-id="332ce-178">关闭</span><span class="sxs-lookup"><span data-stu-id="332ce-178">Off</span></span> | <span data-ttu-id="332ce-179">否</span><span class="sxs-lookup"><span data-stu-id="332ce-179">No</span></span> | <span data-ttu-id="332ce-180">此功能已关闭。</span><span class="sxs-lookup"><span data-stu-id="332ce-180">This feature is turned off.</span></span>  |  
| Favorites | <span data-ttu-id="332ce-181">关闭</span><span class="sxs-lookup"><span data-stu-id="332ce-181">Off</span></span> | <span data-ttu-id="332ce-182">否</span><span class="sxs-lookup"><span data-stu-id="332ce-182">No</span></span> | <span data-ttu-id="332ce-183">此功能已关闭。</span><span class="sxs-lookup"><span data-stu-id="332ce-183">This feature is turned off.</span></span>  |  
| IE Mode | <span data-ttu-id="332ce-184">关闭</span><span class="sxs-lookup"><span data-stu-id="332ce-184">Off</span></span> | <span data-ttu-id="332ce-185">否</span><span class="sxs-lookup"><span data-stu-id="332ce-185">No</span></span> | <span data-ttu-id="332ce-186">此功能已关闭。</span><span class="sxs-lookup"><span data-stu-id="332ce-186">This feature is turned off.</span></span>  |  
| Immersive Reader | <span data-ttu-id="332ce-187">关闭</span><span class="sxs-lookup"><span data-stu-id="332ce-187">Off</span></span> | <span data-ttu-id="332ce-188">否</span><span class="sxs-lookup"><span data-stu-id="332ce-188">No</span></span> | <span data-ttu-id="332ce-189">此功能取决于用于交互的浏览器 UI。</span><span class="sxs-lookup"><span data-stu-id="332ce-189">This feature depends on the browser UI for interaction.</span></span>  <span data-ttu-id="332ce-190">此功能已关闭。</span><span class="sxs-lookup"><span data-stu-id="332ce-190">This feature is turned off.</span></span>  |  
| Intrusive Ads | <span data-ttu-id="332ce-191">关闭</span><span class="sxs-lookup"><span data-stu-id="332ce-191">Off</span></span> | <span data-ttu-id="332ce-192">否</span><span class="sxs-lookup"><span data-stu-id="332ce-192">No</span></span> | <span data-ttu-id="332ce-193">此功能已关闭。</span><span class="sxs-lookup"><span data-stu-id="332ce-193">This feature is turned off.</span></span>  |  
| <span data-ttu-id="332ce-194">键盘快捷方式</span><span class="sxs-lookup"><span data-stu-id="332ce-194">Keyboard shortcuts</span></span> | <span data-ttu-id="332ce-195">查看详细信息</span><span class="sxs-lookup"><span data-stu-id="332ce-195">Review Details</span></span> | <span data-ttu-id="332ce-196">查看详细信息</span><span class="sxs-lookup"><span data-stu-id="332ce-196">Review Details</span></span> | <span data-ttu-id="332ce-197">默认情况下关闭的键盘快捷方式在 WebView2 中没有意义或导致问题。</span><span class="sxs-lookup"><span data-stu-id="332ce-197">The keyboard shortcuts that are turned off by default either don't make sense or cause problems in WebView2.</span></span>  <span data-ttu-id="332ce-198">不得打开或关闭这些快捷方式。</span><span class="sxs-lookup"><span data-stu-id="332ce-198">You may not turn on or off these shortcuts.</span></span>  <span data-ttu-id="332ce-199">相反，您可以使用 事件侦听组合键 `AcceleratorKeyPressed` ，并根据需要创建自定义响应。</span><span class="sxs-lookup"><span data-stu-id="332ce-199">Instead, you may listen for a key combination using the `AcceleratorKeyPressed` event and create a custom response if needed.</span></span>  <span data-ttu-id="332ce-200">有关详细信息，请导航到"[其他键盘快捷方式信息"。](#additional-keyboard-shortcuts-information)</span><span class="sxs-lookup"><span data-stu-id="332ce-200">For more information, navigate to [Additional keyboard shortcuts information](#additional-keyboard-shortcuts-information).</span></span> |  
| Read Aloud | <span data-ttu-id="332ce-201">关闭</span><span class="sxs-lookup"><span data-stu-id="332ce-201">Off</span></span> | <span data-ttu-id="332ce-202">否</span><span class="sxs-lookup"><span data-stu-id="332ce-202">No</span></span> | <span data-ttu-id="332ce-203">此功能已关闭。</span><span class="sxs-lookup"><span data-stu-id="332ce-203">This feature is turned off.</span></span>  |  
| Smart Screen | <span data-ttu-id="332ce-204">开</span><span class="sxs-lookup"><span data-stu-id="332ce-204">On</span></span>`*` | <span data-ttu-id="332ce-205">否</span><span class="sxs-lookup"><span data-stu-id="332ce-205">No</span></span> | `*` <span data-ttu-id="332ce-206">此功能的 UI 已删除，但基础功能仍然可用。</span><span class="sxs-lookup"><span data-stu-id="332ce-206">The UI for this feature has been removed, however the underlying functionality is still available.</span></span>  <span data-ttu-id="332ce-207">此外，您还可以关闭 Smart Screen 使用命令行开关。</span><span class="sxs-lookup"><span data-stu-id="332ce-207">Additionally, you may turn off Smart Screen using a command-line switch.</span></span>  |  
| Translate | <span data-ttu-id="332ce-208">关闭</span><span class="sxs-lookup"><span data-stu-id="332ce-208">Off</span></span> | <span data-ttu-id="332ce-209">否</span><span class="sxs-lookup"><span data-stu-id="332ce-209">No</span></span> | <span data-ttu-id="332ce-210">此功能已关闭。</span><span class="sxs-lookup"><span data-stu-id="332ce-210">This feature is turned off.</span></span>  |  
| Tracking Prevention | <span data-ttu-id="332ce-211">开</span><span class="sxs-lookup"><span data-stu-id="332ce-211">On</span></span>`*` | <span data-ttu-id="332ce-212">否</span><span class="sxs-lookup"><span data-stu-id="332ce-212">No</span></span> | `*` <span data-ttu-id="332ce-213">此功能的 UI 已删除，但基础功能仍然可用。</span><span class="sxs-lookup"><span data-stu-id="332ce-213">The UI for this feature has been removed, however the underlying functionality is still available.</span></span>  <span data-ttu-id="332ce-214">跟踪防护始终设置为平衡。</span><span class="sxs-lookup"><span data-stu-id="332ce-214">Tracking prevention is always set to balanced.</span></span>|  
| Profile and Identity | <span data-ttu-id="332ce-215">关闭</span><span class="sxs-lookup"><span data-stu-id="332ce-215">Off</span></span> | <span data-ttu-id="332ce-216">否</span><span class="sxs-lookup"><span data-stu-id="332ce-216">No</span></span> | <span data-ttu-id="332ce-217">同步收藏夹、Cookie 等的功能已关闭。</span><span class="sxs-lookup"><span data-stu-id="332ce-217">The feature that syncs your favorites, cookies, and so on, is turned off.</span></span>  |  
| Web Payment API | <span data-ttu-id="332ce-218">关闭</span><span class="sxs-lookup"><span data-stu-id="332ce-218">Off</span></span> | <span data-ttu-id="332ce-219">否</span><span class="sxs-lookup"><span data-stu-id="332ce-219">No</span></span> | <span data-ttu-id="332ce-220">此功能已关闭。</span><span class="sxs-lookup"><span data-stu-id="332ce-220">This feature is turned off.</span></span>  | 
| Windows Defender Application Guard | <span data-ttu-id="332ce-221">关闭</span><span class="sxs-lookup"><span data-stu-id="332ce-221">Off</span></span> | <span data-ttu-id="332ce-222">否</span><span class="sxs-lookup"><span data-stu-id="332ce-222">No</span></span> | <span data-ttu-id="332ce-223">此功能已关闭。</span><span class="sxs-lookup"><span data-stu-id="332ce-223">This feature is turned off.</span></span>  |  
| edge:// URLs | <span data-ttu-id="332ce-224">查看详细信息</span><span class="sxs-lookup"><span data-stu-id="332ce-224">Review Details</span></span> | <span data-ttu-id="332ce-225">否</span><span class="sxs-lookup"><span data-stu-id="332ce-225">No</span></span> | <span data-ttu-id="332ce-226">Microsoft Edge 浏览器的设置位于 `edge://` URL 上。</span><span class="sxs-lookup"><span data-stu-id="332ce-226">Settings for the Microsoft Edge browser are on `edge://` URLs.</span></span>  <span data-ttu-id="332ce-227">由于这些网页中的大多数都使用 Microsoft Edge 品牌，或在 WebView2 的上下文中没有意义，因此其中一些 URL 已关闭。</span><span class="sxs-lookup"><span data-stu-id="332ce-227">Because most of these webpages have Microsoft Edge branding or don't make sense within the context of WebView2, some of these URLs are turned off.</span></span>  <span data-ttu-id="332ce-228">有关详细信息，请导航到["阻止的内部 URL"。](#blocked-internal-urls)</span><span class="sxs-lookup"><span data-stu-id="332ce-228">For more information, navigate to [Blocked internal URLs](#blocked-internal-urls).</span></span>  |  

## <a name="blocked-internal-urls"></a><span data-ttu-id="332ce-229">阻止的内部 URL</span><span class="sxs-lookup"><span data-stu-id="332ce-229">Blocked internal URLs</span></span>  

<span data-ttu-id="332ce-230">以下 Microsoft Edge 和 Google Chrome 设置网页在 WebView2 中不可用。</span><span class="sxs-lookup"><span data-stu-id="332ce-230">The following Microsoft Edge and Google Chrome settings webpages aren't available in WebView2.</span></span>  

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

## <a name="additional-keyboard-shortcuts-information"></a><span data-ttu-id="332ce-231">其他键盘快捷方式信息</span><span class="sxs-lookup"><span data-stu-id="332ce-231">Additional keyboard shortcuts information</span></span>  

<span data-ttu-id="332ce-232">Microsoft Edge 和 WebView2 支持键盘快捷方式或键绑定。</span><span class="sxs-lookup"><span data-stu-id="332ce-232">Keyboard shortcuts or key bindings are supported in Microsoft Edge and WebView2.</span></span>  <span data-ttu-id="332ce-233">Microsoft Edge 更新时，默认键绑定可能会更改。</span><span class="sxs-lookup"><span data-stu-id="332ce-233">When Microsoft Edge updates, the default key bindings may change.</span></span>  <span data-ttu-id="332ce-234">此外，如果 WebView2 现在支持此功能，则默认情况下关闭的键盘快捷方式可能会打开。</span><span class="sxs-lookup"><span data-stu-id="332ce-234">Furthermore, a keyboard shortcut that is turned off by default may turn on if the feature is now supported in WebView2.</span></span>  <span data-ttu-id="332ce-235">若要避免更改键盘快捷方式，可以设置为 ，这将关闭访问浏览器功能的所有键，但会启用所有基本的文本编辑和移动 `AreBrowserAcceleratorKeysEnabled` `FALSE` 快捷方式。</span><span class="sxs-lookup"><span data-stu-id="332ce-235">To avoid changes to your keyboard shortcuts, you may set `AreBrowserAcceleratorKeysEnabled` to `FALSE`, which turns off all keys that access browser features, but keeps all basic text-editing and movement shortcuts turned on.</span></span>  

<span data-ttu-id="332ce-236">下表列出了 WebView2 中始终关闭的快捷方式。</span><span class="sxs-lookup"><span data-stu-id="332ce-236">The following table lists the shortcuts that are always turned off in WebView2.</span></span>  <span data-ttu-id="332ce-237">星号 \ (\) 字符指示快捷方式未关闭，但它访问的功能已关闭或不适用于 `*` WebView2。</span><span class="sxs-lookup"><span data-stu-id="332ce-237">An asterisk \(`*`\) character indicates that the shortcut isn't turned off, but the feature it accesses is turned off or doesn't apply to WebView2.</span></span>  

| <span data-ttu-id="332ce-238">操作</span><span class="sxs-lookup"><span data-stu-id="332ce-238">Action</span></span> | <span data-ttu-id="332ce-239">Windows</span><span class="sxs-lookup"><span data-stu-id="332ce-239">Windows</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="332ce-240">添加到</span><span class="sxs-lookup"><span data-stu-id="332ce-240">Add to</span></span> Favorites | `Ctrl`+`D` |  
| <span data-ttu-id="332ce-241">将所有选项卡添加到</span><span class="sxs-lookup"><span data-stu-id="332ce-241">Add All Tabs to</span></span> Favorites | `Ctrl`+`Shift`+`D` |  
| <span data-ttu-id="332ce-242">焦点位置</span><span class="sxs-lookup"><span data-stu-id="332ce-242">Focus Location</span></span> | `Ctrl`+`L, Alt`+`D` |  
| <span data-ttu-id="332ce-243">粘贴并转到</span><span class="sxs-lookup"><span data-stu-id="332ce-243">Paste and Go</span></span> | `Ctrl`+`Shift`+`L` |  
| <span data-ttu-id="332ce-244">打开文件</span><span class="sxs-lookup"><span data-stu-id="332ce-244">Open File</span></span> | `Ctrl`+`O` |  
| Read Aloud `*` | `Ctrl`+`Shift`+`U` |  
| <span data-ttu-id="332ce-245">Web 捕获</span><span class="sxs-lookup"><span data-stu-id="332ce-245">Web Capture</span></span> `*` | `Ctrl`+`Shift`+`S` |  
| <span data-ttu-id="332ce-246">边栏</span><span class="sxs-lookup"><span data-stu-id="332ce-246">Sidebar</span></span> `*` | `Ctrl`+`Shift`+`E` |  
| <span data-ttu-id="332ce-247">保存页面</span><span class="sxs-lookup"><span data-stu-id="332ce-247">Save Page</span></span> | `Ctrl`+`S` |  
| <span data-ttu-id="332ce-248">选择最后一个选项卡</span><span class="sxs-lookup"><span data-stu-id="332ce-248">Select Last Tab</span></span> | `Ctrl`+`9` |  
| <span data-ttu-id="332ce-249">选择下一个选项卡</span><span class="sxs-lookup"><span data-stu-id="332ce-249">Select Next Tab</span></span> | `Ctrl`+`Tab` |  
| <span data-ttu-id="332ce-250">选择上一个选项卡</span><span class="sxs-lookup"><span data-stu-id="332ce-250">Select Previous Tab</span></span> | `Ctrl`+`Shift`+`Tab` |  
| <span data-ttu-id="332ce-251">选择选项卡 \ (1 - 8\) </span><span class="sxs-lookup"><span data-stu-id="332ce-251">Select Tab \(1 - 8\)</span></span> | `Ctrl`+`(1-8)` |  
| <span data-ttu-id="332ce-252">显示 Favorites 栏</span><span class="sxs-lookup"><span data-stu-id="332ce-252">Show Favorites Bar</span></span> `*` | `Ctrl`+`Shift`+`B` |  
| <span data-ttu-id="332ce-253">帮助</span><span class="sxs-lookup"><span data-stu-id="332ce-253">Help</span></span> | `F1` |  
| <span data-ttu-id="332ce-254">焦点下一个窗格</span><span class="sxs-lookup"><span data-stu-id="332ce-254">Focus Next Pane</span></span> `*` | `F6` |  
| <span data-ttu-id="332ce-255">焦点上一个窗格</span><span class="sxs-lookup"><span data-stu-id="332ce-255">Focus Previous Pane</span></span> `*` | `Shift`+`F6` |  
| <span data-ttu-id="332ce-256">项目浏览</span><span class="sxs-lookup"><span data-stu-id="332ce-256">Caret Browsing</span></span> `*` | `F7` |  
| <span data-ttu-id="332ce-257">阅读视图</span><span class="sxs-lookup"><span data-stu-id="332ce-257">Reading View</span></span> `*` | `F9` |  
| <span data-ttu-id="332ce-258">焦点菜单栏</span><span class="sxs-lookup"><span data-stu-id="332ce-258">Focus Menu Bar</span></span> | `F10` |  
| <span data-ttu-id="332ce-259">显示标识菜单</span><span class="sxs-lookup"><span data-stu-id="332ce-259">Show Identity Menu</span></span> `*` | `Ctrl`+`Shift`+`M` |  
| Browser Task Manager `*` | `Shift`+`Escape` |  
| <span data-ttu-id="332ce-260">Edge 反馈</span><span class="sxs-lookup"><span data-stu-id="332ce-260">Edge Feedback</span></span> `*` | `Shift`+`Alt`+`I` |  
| <span data-ttu-id="332ce-261">静音选项卡</span><span class="sxs-lookup"><span data-stu-id="332ce-261">Mute Tab</span></span> `*` | `Ctrl`+`M` |  
| <span data-ttu-id="332ce-262">新建隐身窗口</span><span class="sxs-lookup"><span data-stu-id="332ce-262">New Incognito Window</span></span> | `Ctrl`+`Shift`+`N` |  
| <span data-ttu-id="332ce-263">新建选项卡</span><span class="sxs-lookup"><span data-stu-id="332ce-263">New Tab</span></span> | `Ctrl`+`T` |  
| <span data-ttu-id="332ce-264">新建窗口</span><span class="sxs-lookup"><span data-stu-id="332ce-264">New Window</span></span> | `Ctrl`+`N` |  
| <span data-ttu-id="332ce-265">"还原上次关闭"选项卡</span><span class="sxs-lookup"><span data-stu-id="332ce-265">Restore Last Closed Tab</span></span> | `Ctrl`+`Shift`+`T` |  
| <span data-ttu-id="332ce-266">对焦</span><span class="sxs-lookup"><span data-stu-id="332ce-266">Focus</span></span> Favorites | `Alt`+`Shift`+`B` |  
| <span data-ttu-id="332ce-267">焦点非活动弹出窗口</span><span class="sxs-lookup"><span data-stu-id="332ce-267">Focus Inactive Popup</span></span> | `Alt`+`Shift`+`A` |  
| <span data-ttu-id="332ce-268">焦点搜索</span><span class="sxs-lookup"><span data-stu-id="332ce-268">Focus Search</span></span> | `Ctrl`<span data-ttu-id="332ce-269">+`E`, `Ctrl`+`K`,</span><span class="sxs-lookup"><span data-stu-id="332ce-269">+`E`, `Ctrl`+`K`,</span></span> `Search Key` |  
| <span data-ttu-id="332ce-270">"重复"选项卡</span><span class="sxs-lookup"><span data-stu-id="332ce-270">Duplicate Tab</span></span> | `Ctrl`+`Shift`+`K` |  
| <span data-ttu-id="332ce-271">焦点工具栏</span><span class="sxs-lookup"><span data-stu-id="332ce-271">Focus Toolbar</span></span> `*` | `Alt`+`Shift`+`T` |  
| <span data-ttu-id="332ce-272">主页</span><span class="sxs-lookup"><span data-stu-id="332ce-272">Home</span></span> | `Alt`<span data-ttu-id="332ce-273">+`Home`,</span><span class="sxs-lookup"><span data-stu-id="332ce-273">+`Home`,</span></span> `Browser Home Key` |  
| <span data-ttu-id="332ce-274">显示应用菜单</span><span class="sxs-lookup"><span data-stu-id="332ce-274">Show App Menu</span></span> | `Alt`+`E, Alt`+`F` |  
| <span data-ttu-id="332ce-275">显示</span><span class="sxs-lookup"><span data-stu-id="332ce-275">Show</span></span> Favorites | `Ctrl`+`Shift`+`O` |  
| <span data-ttu-id="332ce-276">显示</span><span class="sxs-lookup"><span data-stu-id="332ce-276">Show</span></span> Downloads | `Ctrl`+`J` |  
| <span data-ttu-id="332ce-277">显示历史记录</span><span class="sxs-lookup"><span data-stu-id="332ce-277">Show History</span></span> | `Ctrl`+`H` |  
| <span data-ttu-id="332ce-278">显示阅读模式栏</span><span class="sxs-lookup"><span data-stu-id="332ce-278">Show Reading Mode Bar</span></span> `*` | `Shift`+`Alt`+`R` |  
| <span data-ttu-id="332ce-279">显示</span><span class="sxs-lookup"><span data-stu-id="332ce-279">Show</span></span> Collections `*` | `Ctrl`+`Shift`+`Y` |  

<span data-ttu-id="332ce-280">以下键盘快捷方式始终关闭，在未处理事件时显示的窗口中 `NewWindowRequested` 除外。</span><span class="sxs-lookup"><span data-stu-id="332ce-280">The following keyboard shortcuts are always turned off, except in windows that display when the `NewWindowRequested` event isn't handled.</span></span>

| <span data-ttu-id="332ce-281">操作</span><span class="sxs-lookup"><span data-stu-id="332ce-281">Action</span></span> | <span data-ttu-id="332ce-282">Windows</span><span class="sxs-lookup"><span data-stu-id="332ce-282">Windows</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="332ce-283">关闭选项卡</span><span class="sxs-lookup"><span data-stu-id="332ce-283">Close Tab</span></span> | `Ctrl`+`W, Ctrl`+`F4` |  
| <span data-ttu-id="332ce-284">关闭窗口</span><span class="sxs-lookup"><span data-stu-id="332ce-284">Close Window</span></span> | `Ctrl`+`Shift`+`W` |  
| <span data-ttu-id="332ce-285">全屏</span><span class="sxs-lookup"><span data-stu-id="332ce-285">Fullscreen</span></span> | `F11` |  

<span data-ttu-id="332ce-286">如果设置为 `AreBrowserAcceleratorKeysEnabled` `FALSE` ，则以下其他键盘快捷方式将关闭。</span><span class="sxs-lookup"><span data-stu-id="332ce-286">If you set `AreBrowserAcceleratorKeysEnabled` to `FALSE`, the following additional keyboard shortcuts are turned off.</span></span>  

| <span data-ttu-id="332ce-287">操作</span><span class="sxs-lookup"><span data-stu-id="332ce-287">Action</span></span> | <span data-ttu-id="332ce-288">Windows</span><span class="sxs-lookup"><span data-stu-id="332ce-288">Windows</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="332ce-289">停止</span><span class="sxs-lookup"><span data-stu-id="332ce-289">Stop</span></span> | `Escape` |  
| <span data-ttu-id="332ce-290">在页面上查找</span><span class="sxs-lookup"><span data-stu-id="332ce-290">Find on Page</span></span> | `Ctrl`+`F` |  
| <span data-ttu-id="332ce-291">查找下一个</span><span class="sxs-lookup"><span data-stu-id="332ce-291">Find Next</span></span> | `Ctrl`+`G` |  
| <span data-ttu-id="332ce-292">查找上一个</span><span class="sxs-lookup"><span data-stu-id="332ce-292">Find Previous</span></span> | `Ctrl`+`Shift`+`G` |  
| <span data-ttu-id="332ce-293">Print</span><span class="sxs-lookup"><span data-stu-id="332ce-293">Print</span></span> | `Ctrl`+`P` |  
| <span data-ttu-id="332ce-294">刷新</span><span class="sxs-lookup"><span data-stu-id="332ce-294">Refresh</span></span> | `Ctrl`<span data-ttu-id="332ce-295">+`R`, `F5`,</span><span class="sxs-lookup"><span data-stu-id="332ce-295">+`R`, `F5`,</span></span> `Reload Key` |  
| <span data-ttu-id="332ce-296">刷新（不含缓存）</span><span class="sxs-lookup"><span data-stu-id="332ce-296">Refresh Without Cache</span></span> | `Ctrl`<span data-ttu-id="332ce-297">+`Shift`+`R`, `Ctrl`+`F5`, `Shift`+`F5`, `Ctrl`+`Refresh`, `Shift`+</span><span class="sxs-lookup"><span data-stu-id="332ce-297">+`Shift`+`R`, `Ctrl`+`F5`, `Shift`+`F5`, `Ctrl`+`Refresh`, `Shift`+</span></span>`Refresh` |  
| <span data-ttu-id="332ce-298">缩小</span><span class="sxs-lookup"><span data-stu-id="332ce-298">Zoom Out</span></span> | `Ctrl`+`-` |  
| <span data-ttu-id="332ce-299">放大</span><span class="sxs-lookup"><span data-stu-id="332ce-299">Zoom In</span></span> | `Ctrl`+`+` |  
| <span data-ttu-id="332ce-300">重置缩放</span><span class="sxs-lookup"><span data-stu-id="332ce-300">Reset Zoom</span></span> | `Ctrl`+`0` |  
| <span data-ttu-id="332ce-301">查找下一个</span><span class="sxs-lookup"><span data-stu-id="332ce-301">Find Next</span></span> | `F3` |  
| <span data-ttu-id="332ce-302">查找上一个</span><span class="sxs-lookup"><span data-stu-id="332ce-302">Find Previous</span></span> | `Shift`+`F3` |  
| <span data-ttu-id="332ce-303">后退</span><span class="sxs-lookup"><span data-stu-id="332ce-303">Back</span></span> | `Alt`+`Left, Browser Back Key` |  
| <span data-ttu-id="332ce-304">前进</span><span class="sxs-lookup"><span data-stu-id="332ce-304">Forward</span></span> | `Alt`<span data-ttu-id="332ce-305">+`Right`,</span><span class="sxs-lookup"><span data-stu-id="332ce-305">+`Right`,</span></span> `Browser Forward Key` |  
| <span data-ttu-id="332ce-306">Print</span><span class="sxs-lookup"><span data-stu-id="332ce-306">Print</span></span> | `Ctrl`+`P` |  
| <span data-ttu-id="332ce-307">打开/关闭 DevTools</span><span class="sxs-lookup"><span data-stu-id="332ce-307">Open / Close DevTools</span></span> | `Ctrl`+`Shift`+`I` |  
| <span data-ttu-id="332ce-308">打开 DevTools 控制台</span><span class="sxs-lookup"><span data-stu-id="332ce-308">Open DevTools Console</span></span> | `Ctrl`+`Shift`+`J` |  
| <span data-ttu-id="332ce-309">打开 DevTools Inspect</span><span class="sxs-lookup"><span data-stu-id="332ce-309">Open DevTools Inspect</span></span> | `Ctrl`+`Shift`+`C` |  

> [!Note] 
> <span data-ttu-id="332ce-310">若要单独自定义任何键，请使用 [AcceleratorKeyPressed][DotnetApiMicrosoftWebWebview2CoreCorewebview2controllerAcceleratorkeypressedViewWebview2Dotnet1077444] 事件。</span><span class="sxs-lookup"><span data-stu-id="332ce-310">To customize any of the keys individually, use the [AcceleratorKeyPressed][DotnetApiMicrosoftWebWebview2CoreCorewebview2controllerAcceleratorkeypressedViewWebview2Dotnet1077444] event.</span></span>  
  
  
## <a name="getting-in-touch-with-the-microsoft-edge-webview2-team"></a><span data-ttu-id="332ce-311">与 Microsoft Edge WebView2 团队联系</span><span class="sxs-lookup"><span data-stu-id="332ce-311">Getting in touch with the Microsoft Edge WebView2 team</span></span>  

[!INCLUDE [contact WebView2 team note](../includes/contact-webview-team-note.md)]  

<!-- links -->  

<!--[Webview2ReferenceDownloadApi]: ./download-api.md "download API | Microsoft Docs"  -->  

[DotnetApiMicrosoftWebWebview2CoreCorewebview2controllerAcceleratorkeypressedViewWebview2Dotnet1077444]: /dotnet/api/microsoft.web.webview2.core.corewebview2controller.acceleratorkeypressed?view=webview2-dotnet-1.0.774.44&preserve-view=true "CoreWebView2Controller.AcceleratorKeyPressed 事件|Microsoft Docs"  

[DevtoolsShortcutsIndex]: ../../devtools-guide-chromium/shortcuts/index.md "Microsoft Edge DevTools 键盘快捷方式 | Microsoft Docs"  

[PeterExperimentsChromiumCommandLineSwitches]: https://peter.sh/experiments/chromium-command-line-switches "Chromium 命令行开关列表|Peter Beverloo"  
