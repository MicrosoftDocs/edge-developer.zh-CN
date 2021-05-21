---
description: Microsoft Edge 和 WebView2 标题之间的功能差异
title: Microsoft Edge 和 WebView2 之间的功能差异作者
ms.author: msedgedevrel
ms.date: 05/06/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2, IWebView2WebView, WebView2, webview, wpf apps, wpf, edge, ICoreWebView2, ICoreWebView2Host, browser control, edge html
no-loc: ["Autofill for Addresses", "Autofill for Passwords", Autofill for Payments", Browser Extensions", "Browser Task Manager", "Collections", "Continue-where-I-left-off prompt", "Downloads", "Edge Shopping", "Family Safety", "Favorites", "Hotkeys", "IE Mode" ,"Immersive Reader", "Intrusive Ads", "Read Aloud", "Smart Screen", "Translate", "Tracking Prevention", "Profile and Identity", "Web Payment API", "Windows Defender Application Guard","edge:// URLs"]  
---
# <a name="browser-feature-differences-between-microsoft-edge-and-webview2"></a><span data-ttu-id="0be31-125">Microsoft Edge 和 WebView2 之间的浏览器功能差异</span><span class="sxs-lookup"><span data-stu-id="0be31-125">Browser feature differences between Microsoft Edge and WebView2</span></span>  

<span data-ttu-id="0be31-126">WebView2 基于新的 Microsoft Edge 浏览器。</span><span class="sxs-lookup"><span data-stu-id="0be31-126">WebView2 is based on the new Microsoft Edge browser.</span></span>  <span data-ttu-id="0be31-127">你有机会将功能从浏览器扩展到基于 WebView2 的应用，这很有用。</span><span class="sxs-lookup"><span data-stu-id="0be31-127">You have the opportunity to extend features from the browser to WebView2-based apps, which is useful.</span></span>  <span data-ttu-id="0be31-128">但是，由于 WebView2 不限于类似浏览器的应用，因此需要修改或删除一些浏览器功能。</span><span class="sxs-lookup"><span data-stu-id="0be31-128">However, since WebView2 isn't limited to browser-like apps, there are some browser features that need to be modified or removed.</span></span>  <span data-ttu-id="0be31-129">本文提供以下信息。</span><span class="sxs-lookup"><span data-stu-id="0be31-129">This article provides the following information.</span></span>  

*   <span data-ttu-id="0be31-130">修改后的浏览器功能和支持信息。</span><span class="sxs-lookup"><span data-stu-id="0be31-130">The modified browser features and supporting information.</span></span>   
*   <span data-ttu-id="0be31-131">启用或关闭功能的功能。</span><span class="sxs-lookup"><span data-stu-id="0be31-131">The ability to turn on or off the feature.</span></span>  
*   <span data-ttu-id="0be31-132">有关键盘快捷方式的指南。</span><span class="sxs-lookup"><span data-stu-id="0be31-132">Guidance on keyboard shortcuts.</span></span>  
    
## <a name="design-guidelines"></a><span data-ttu-id="0be31-133">设计指南</span><span class="sxs-lookup"><span data-stu-id="0be31-133">Design guidelines</span></span>  

<span data-ttu-id="0be31-134">在 WebView2 上下文中，浏览器功能遵循以下设计准则。</span><span class="sxs-lookup"><span data-stu-id="0be31-134">In the context of WebView2, browser features adhere to the following design guidelines.</span></span>  

*   <span data-ttu-id="0be31-135">大多数功能在 WebView2 和 Microsoft Edge 中都相同。</span><span class="sxs-lookup"><span data-stu-id="0be31-135">Most features work the same in WebView2 and Microsoft Edge.</span></span>  <span data-ttu-id="0be31-136">如果功能在 WebView2 上下文中不起作用或出于其他原因，则功能会修改或关闭。</span><span class="sxs-lookup"><span data-stu-id="0be31-136">If a feature doesn't make sense in the context of WebView2 or for other reasons, the feature is modified or turned off.</span></span> 
*   <span data-ttu-id="0be31-137">WebView2 功能不包括 Microsoft Edge 品牌。</span><span class="sxs-lookup"><span data-stu-id="0be31-137">WebView2 features don't include Microsoft Edge branding.</span></span>  
    
## <a name="features"></a><span data-ttu-id="0be31-138">功能</span><span class="sxs-lookup"><span data-stu-id="0be31-138">Features</span></span>  

<span data-ttu-id="0be31-139">下表显示了与 Microsoft Edge 浏览器不同的 WebView2 功能。</span><span class="sxs-lookup"><span data-stu-id="0be31-139">The following table displays the WebView2 features that differ from the Microsoft Edge browser.</span></span>   

*   <span data-ttu-id="0be31-140">**默认** 状态指示功能是新 WebView2 实例上默认体验的一部分。</span><span class="sxs-lookup"><span data-stu-id="0be31-140">**Default state** indicates that the feature is part of the default experience on a new WebView2 instance.</span></span>  
*   <span data-ttu-id="0be31-141">**可** 配置指示可以使用 WebView2 API 或命令行开关打开或关闭该功能。</span><span class="sxs-lookup"><span data-stu-id="0be31-141">**Configurable** indicates that you may turn on or off the feature using WebView2 APIs or command-line switches.</span></span>  
    
> [!NOTE]  
> <span data-ttu-id="0be31-142">本文不介绍使用命令行开关修改功能。</span><span class="sxs-lookup"><span data-stu-id="0be31-142">This article doesn't cover modifying features using command-line switches.</span></span>  <span data-ttu-id="0be31-143">有关使用命令行开关打开和关闭功能的信息，请导航到 [Chromium 命令行开关的列表][PeterExperimentsChromiumCommandLineSwitches]。</span><span class="sxs-lookup"><span data-stu-id="0be31-143">For more information about turning on and off features with command-line switches, navigate to [List of Chromium Command Line Switches][PeterExperimentsChromiumCommandLineSwitches].</span></span>  
    
| <span data-ttu-id="0be31-144">功能</span><span class="sxs-lookup"><span data-stu-id="0be31-144">Feature</span></span> | <span data-ttu-id="0be31-145">默认状态</span><span class="sxs-lookup"><span data-stu-id="0be31-145">Default state</span></span> | <span data-ttu-id="0be31-146">可配置</span><span class="sxs-lookup"><span data-stu-id="0be31-146">Configurable</span></span> | <span data-ttu-id="0be31-147">详细信息</span><span class="sxs-lookup"><span data-stu-id="0be31-147">Details</span></span> |  
|:--- |:--- |:--- | :--- |  
| Autofill for Addresses | <span data-ttu-id="0be31-148">开</span><span class="sxs-lookup"><span data-stu-id="0be31-148">On</span></span> | <span data-ttu-id="0be31-149">是</span><span class="sxs-lookup"><span data-stu-id="0be31-149">Yes</span></span> | <span data-ttu-id="0be31-150">默认情况下，此功能已打开，可以使用 WebView2 自动填充 API 将其打开或关闭。</span><span class="sxs-lookup"><span data-stu-id="0be31-150">This feature is turned on by default, you may turn it on or off using WebView2 Autofill APIs.</span></span>  |  
| Autofill for Passwords | <span data-ttu-id="0be31-151">开</span><span class="sxs-lookup"><span data-stu-id="0be31-151">On</span></span> | <span data-ttu-id="0be31-152">是</span><span class="sxs-lookup"><span data-stu-id="0be31-152">Yes</span></span> | <span data-ttu-id="0be31-153">默认情况下，此功能已打开，可以使用 WebView2 自动填充 API 将其打开或关闭。</span><span class="sxs-lookup"><span data-stu-id="0be31-153">This feature is turned on by default, you may turn it on or off using WebView2 Autofill APIs.</span></span>  |  
| <span data-ttu-id="0be31-154">付款自动填充</span><span class="sxs-lookup"><span data-stu-id="0be31-154">Autofill for Payments</span></span> | <span data-ttu-id="0be31-155">关闭</span><span class="sxs-lookup"><span data-stu-id="0be31-155">Off</span></span> | <span data-ttu-id="0be31-156">否</span><span class="sxs-lookup"><span data-stu-id="0be31-156">No</span></span> | <span data-ttu-id="0be31-157">此功能已关闭。</span><span class="sxs-lookup"><span data-stu-id="0be31-157">This feature is turned off.</span></span>  |  
| <span data-ttu-id="0be31-158">浏览器扩展</span><span class="sxs-lookup"><span data-stu-id="0be31-158">Browser Extensions</span></span> | <span data-ttu-id="0be31-159">关闭</span><span class="sxs-lookup"><span data-stu-id="0be31-159">Off</span></span> | <span data-ttu-id="0be31-160">否</span><span class="sxs-lookup"><span data-stu-id="0be31-160">No</span></span> | <span data-ttu-id="0be31-161">此功能已关闭。</span><span class="sxs-lookup"><span data-stu-id="0be31-161">This feature is turned off.</span></span>  |  
| Browser Task Manager | <span data-ttu-id="0be31-162">关闭</span><span class="sxs-lookup"><span data-stu-id="0be31-162">Off</span></span> | <span data-ttu-id="0be31-163">否</span><span class="sxs-lookup"><span data-stu-id="0be31-163">No</span></span> | <span data-ttu-id="0be31-164">此功能已关闭。</span><span class="sxs-lookup"><span data-stu-id="0be31-164">This feature is turned off.</span></span>  |  
| Collections | <span data-ttu-id="0be31-165">关闭</span><span class="sxs-lookup"><span data-stu-id="0be31-165">Off</span></span> | <span data-ttu-id="0be31-166">否</span><span class="sxs-lookup"><span data-stu-id="0be31-166">No</span></span> | <span data-ttu-id="0be31-167">此功能已关闭。</span><span class="sxs-lookup"><span data-stu-id="0be31-167">This feature is turned off.</span></span>  |  
| Continue-where-I-left-off prompt | <span data-ttu-id="0be31-168">关闭</span><span class="sxs-lookup"><span data-stu-id="0be31-168">Off</span></span> | <span data-ttu-id="0be31-169">否</span><span class="sxs-lookup"><span data-stu-id="0be31-169">No</span></span> | <span data-ttu-id="0be31-170">此功能已关闭。</span><span class="sxs-lookup"><span data-stu-id="0be31-170">This feature is turned off.</span></span>  |  
| Downloads | <span data-ttu-id="0be31-171">开</span><span class="sxs-lookup"><span data-stu-id="0be31-171">On</span></span> | <span data-ttu-id="0be31-172">是</span><span class="sxs-lookup"><span data-stu-id="0be31-172">Yes</span></span> | <span data-ttu-id="0be31-173">WebView2 提供了一个 API，允许你自定义下载 UI 以操作下载。</span><span class="sxs-lookup"><span data-stu-id="0be31-173">WebView2 provides an API that allows you to customize the download UI to manipulate downloads.</span></span> <span data-ttu-id="0be31-174">例如，可以阻止、重定向、保存、暂停等。</span><span class="sxs-lookup"><span data-stu-id="0be31-174">For example, you can block, redirect, save, pause, and so on.</span></span>  <!--For more information, navigate to [download API][Webview2ReferenceDownloadApi].--> |  
| Edge Shopping | <span data-ttu-id="0be31-175">关闭</span><span class="sxs-lookup"><span data-stu-id="0be31-175">Off</span></span> | <span data-ttu-id="0be31-176">否</span><span class="sxs-lookup"><span data-stu-id="0be31-176">No</span></span> | <span data-ttu-id="0be31-177">此功能已关闭。</span><span class="sxs-lookup"><span data-stu-id="0be31-177">This feature is turned off.</span></span>  |  
| Family Safety | <span data-ttu-id="0be31-178">关闭</span><span class="sxs-lookup"><span data-stu-id="0be31-178">Off</span></span> | <span data-ttu-id="0be31-179">否</span><span class="sxs-lookup"><span data-stu-id="0be31-179">No</span></span> | <span data-ttu-id="0be31-180">此功能已关闭。</span><span class="sxs-lookup"><span data-stu-id="0be31-180">This feature is turned off.</span></span>  |  
| Favorites | <span data-ttu-id="0be31-181">关闭</span><span class="sxs-lookup"><span data-stu-id="0be31-181">Off</span></span> | <span data-ttu-id="0be31-182">否</span><span class="sxs-lookup"><span data-stu-id="0be31-182">No</span></span> | <span data-ttu-id="0be31-183">此功能已关闭。</span><span class="sxs-lookup"><span data-stu-id="0be31-183">This feature is turned off.</span></span>  |  
| IE Mode | <span data-ttu-id="0be31-184">关闭</span><span class="sxs-lookup"><span data-stu-id="0be31-184">Off</span></span> | <span data-ttu-id="0be31-185">否</span><span class="sxs-lookup"><span data-stu-id="0be31-185">No</span></span> | <span data-ttu-id="0be31-186">此功能已关闭。</span><span class="sxs-lookup"><span data-stu-id="0be31-186">This feature is turned off.</span></span>  |  
| Immersive Reader | <span data-ttu-id="0be31-187">关闭</span><span class="sxs-lookup"><span data-stu-id="0be31-187">Off</span></span> | <span data-ttu-id="0be31-188">否</span><span class="sxs-lookup"><span data-stu-id="0be31-188">No</span></span> | <span data-ttu-id="0be31-189">此功能取决于用于交互的浏览器 UI。</span><span class="sxs-lookup"><span data-stu-id="0be31-189">This feature depends on the browser UI for interaction.</span></span>  <span data-ttu-id="0be31-190">此功能已关闭。</span><span class="sxs-lookup"><span data-stu-id="0be31-190">This feature is turned off.</span></span>  |  
| Intrusive Ads | <span data-ttu-id="0be31-191">关闭</span><span class="sxs-lookup"><span data-stu-id="0be31-191">Off</span></span> | <span data-ttu-id="0be31-192">否</span><span class="sxs-lookup"><span data-stu-id="0be31-192">No</span></span> | <span data-ttu-id="0be31-193">此功能已关闭。</span><span class="sxs-lookup"><span data-stu-id="0be31-193">This feature is turned off.</span></span>  |  
| <span data-ttu-id="0be31-194">键盘快捷方式</span><span class="sxs-lookup"><span data-stu-id="0be31-194">Keyboard shortcuts</span></span> | <span data-ttu-id="0be31-195">查看详细信息</span><span class="sxs-lookup"><span data-stu-id="0be31-195">Review Details</span></span> | <span data-ttu-id="0be31-196">查看详细信息</span><span class="sxs-lookup"><span data-stu-id="0be31-196">Review Details</span></span> | <span data-ttu-id="0be31-197">默认情况下关闭的键盘快捷方式在 WebView2 中没有意义或导致问题。</span><span class="sxs-lookup"><span data-stu-id="0be31-197">The keyboard shortcuts that are turned off by default either don't make sense or cause problems in WebView2.</span></span>  <span data-ttu-id="0be31-198">不得打开或关闭这些快捷方式。</span><span class="sxs-lookup"><span data-stu-id="0be31-198">You may not turn on or off these shortcuts.</span></span>  <span data-ttu-id="0be31-199">相反，您可以使用 事件侦听组合键 `AcceleratorKeyPressed` ，并根据需要创建自定义响应。</span><span class="sxs-lookup"><span data-stu-id="0be31-199">Instead, you may listen for a key combination using the `AcceleratorKeyPressed` event and create a custom response if needed.</span></span>  <span data-ttu-id="0be31-200">有关详细信息，请导航到"[其他键盘快捷方式信息"。](#additional-keyboard-shortcuts-information)</span><span class="sxs-lookup"><span data-stu-id="0be31-200">For more information, navigate to [Additional keyboard shortcuts information](#additional-keyboard-shortcuts-information).</span></span> |  
| <span data-ttu-id="0be31-201">推送通知</span><span class="sxs-lookup"><span data-stu-id="0be31-201">Push notifications</span></span> | <span data-ttu-id="0be31-202">关闭</span><span class="sxs-lookup"><span data-stu-id="0be31-202">Off</span></span> | <span data-ttu-id="0be31-203">否</span><span class="sxs-lookup"><span data-stu-id="0be31-203">No</span></span> | <span data-ttu-id="0be31-204">WebView2 中未实现此功能。</span><span class="sxs-lookup"><span data-stu-id="0be31-204">This feature is not implemented in WebView2.</span></span>  <span data-ttu-id="0be31-205">有关详细信息，请导航到添加对[HTML5 通知 API (#308) 。 ][GithubMicrosoftedgeWebview2feedbackIssues308]</span><span class="sxs-lookup"><span data-stu-id="0be31-205">For more information, navigate to [Add support for HTML5 Notification API (#308)][GithubMicrosoftedgeWebview2feedbackIssues308].</span></span> |  
| Read Aloud | <span data-ttu-id="0be31-206">关闭</span><span class="sxs-lookup"><span data-stu-id="0be31-206">Off</span></span> | <span data-ttu-id="0be31-207">否</span><span class="sxs-lookup"><span data-stu-id="0be31-207">No</span></span> | <span data-ttu-id="0be31-208">此功能已关闭。</span><span class="sxs-lookup"><span data-stu-id="0be31-208">This feature is turned off.</span></span>  |  
| Smart Screen | <span data-ttu-id="0be31-209">开</span><span class="sxs-lookup"><span data-stu-id="0be31-209">On</span></span>`*` | <span data-ttu-id="0be31-210">否</span><span class="sxs-lookup"><span data-stu-id="0be31-210">No</span></span> | `*` <span data-ttu-id="0be31-211">此功能的 UI 已删除，但基础功能仍然可用。</span><span class="sxs-lookup"><span data-stu-id="0be31-211">The UI for this feature has been removed, however the underlying functionality is still available.</span></span>  <span data-ttu-id="0be31-212">此外，您还可以关闭 Smart Screen 使用命令行开关。</span><span class="sxs-lookup"><span data-stu-id="0be31-212">Additionally, you may turn off Smart Screen using a command-line switch.</span></span>  |  
| Translate | <span data-ttu-id="0be31-213">关闭</span><span class="sxs-lookup"><span data-stu-id="0be31-213">Off</span></span> | <span data-ttu-id="0be31-214">否</span><span class="sxs-lookup"><span data-stu-id="0be31-214">No</span></span> | <span data-ttu-id="0be31-215">此功能已关闭。</span><span class="sxs-lookup"><span data-stu-id="0be31-215">This feature is turned off.</span></span>  |  
| Tracking Prevention | <span data-ttu-id="0be31-216">开</span><span class="sxs-lookup"><span data-stu-id="0be31-216">On</span></span>`*` | <span data-ttu-id="0be31-217">否</span><span class="sxs-lookup"><span data-stu-id="0be31-217">No</span></span> | `*` <span data-ttu-id="0be31-218">此功能的 UI 已删除，但基础功能仍然可用。</span><span class="sxs-lookup"><span data-stu-id="0be31-218">The UI for this feature has been removed, however the underlying functionality is still available.</span></span>  <span data-ttu-id="0be31-219">跟踪防护始终设置为平衡。</span><span class="sxs-lookup"><span data-stu-id="0be31-219">Tracking prevention is always set to balanced.</span></span>|  
| Profile and Identity | <span data-ttu-id="0be31-220">关闭</span><span class="sxs-lookup"><span data-stu-id="0be31-220">Off</span></span> | <span data-ttu-id="0be31-221">否</span><span class="sxs-lookup"><span data-stu-id="0be31-221">No</span></span> | <span data-ttu-id="0be31-222">同步收藏夹、Cookie 等的功能已关闭。</span><span class="sxs-lookup"><span data-stu-id="0be31-222">The feature that syncs your favorites, cookies, and so on, is turned off.</span></span>  |  
| Web Payment API | <span data-ttu-id="0be31-223">关闭</span><span class="sxs-lookup"><span data-stu-id="0be31-223">Off</span></span> | <span data-ttu-id="0be31-224">否</span><span class="sxs-lookup"><span data-stu-id="0be31-224">No</span></span> | <span data-ttu-id="0be31-225">此功能已关闭。</span><span class="sxs-lookup"><span data-stu-id="0be31-225">This feature is turned off.</span></span>  | 
| Windows Defender Application Guard | <span data-ttu-id="0be31-226">关闭</span><span class="sxs-lookup"><span data-stu-id="0be31-226">Off</span></span> | <span data-ttu-id="0be31-227">否</span><span class="sxs-lookup"><span data-stu-id="0be31-227">No</span></span> | <span data-ttu-id="0be31-228">此功能已关闭。</span><span class="sxs-lookup"><span data-stu-id="0be31-228">This feature is turned off.</span></span>  |  
| edge:// URLs | <span data-ttu-id="0be31-229">查看详细信息</span><span class="sxs-lookup"><span data-stu-id="0be31-229">Review Details</span></span> | <span data-ttu-id="0be31-230">否</span><span class="sxs-lookup"><span data-stu-id="0be31-230">No</span></span> | <span data-ttu-id="0be31-231">Microsoft Edge 浏览器的设置位于 `edge://` URL 上。</span><span class="sxs-lookup"><span data-stu-id="0be31-231">Settings for the Microsoft Edge browser are on `edge://` URLs.</span></span>  <span data-ttu-id="0be31-232">由于这些网页中的大多数都使用 Microsoft Edge 品牌，或在 WebView2 的上下文中没有意义，因此其中一些 URL 已关闭。</span><span class="sxs-lookup"><span data-stu-id="0be31-232">Because most of these webpages have Microsoft Edge branding or don't make sense within the context of WebView2, some of these URLs are turned off.</span></span>  <span data-ttu-id="0be31-233">有关详细信息，请导航到["阻止的内部 URL"。](#blocked-internal-urls)</span><span class="sxs-lookup"><span data-stu-id="0be31-233">For more information, navigate to [Blocked internal URLs](#blocked-internal-urls).</span></span>  |  

## <a name="blocked-internal-urls"></a><span data-ttu-id="0be31-234">阻止的内部 URL</span><span class="sxs-lookup"><span data-stu-id="0be31-234">Blocked internal URLs</span></span>  

<span data-ttu-id="0be31-235">以下 Microsoft Edge 和 Google Chrome 设置网页在 WebView2 中不可用。</span><span class="sxs-lookup"><span data-stu-id="0be31-235">The following Microsoft Edge and Google Chrome settings webpages aren't available in WebView2.</span></span>  

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
    
## <a name="additional-keyboard-shortcuts-information"></a><span data-ttu-id="0be31-236">其他键盘快捷方式信息</span><span class="sxs-lookup"><span data-stu-id="0be31-236">Additional keyboard shortcuts information</span></span>  

<span data-ttu-id="0be31-237">Microsoft Edge 和 WebView2 支持键盘快捷方式或键绑定。</span><span class="sxs-lookup"><span data-stu-id="0be31-237">Keyboard shortcuts or key bindings are supported in Microsoft Edge and WebView2.</span></span>  <span data-ttu-id="0be31-238">Microsoft Edge 更新时，默认键绑定可能会更改。</span><span class="sxs-lookup"><span data-stu-id="0be31-238">When Microsoft Edge updates, the default key bindings may change.</span></span>  <span data-ttu-id="0be31-239">此外，如果 WebView2 现在支持此功能，则默认情况下关闭的键盘快捷方式可能会打开。</span><span class="sxs-lookup"><span data-stu-id="0be31-239">Furthermore, a keyboard shortcut that is turned off by default may turn on if the feature is now supported in WebView2.</span></span>  <span data-ttu-id="0be31-240">若要避免更改键盘快捷方式，可以设置为 ，这将关闭访问浏览器功能的所有键，但会启用所有基本的文本编辑和移动 `AreBrowserAcceleratorKeysEnabled` `FALSE` 快捷方式。</span><span class="sxs-lookup"><span data-stu-id="0be31-240">To avoid changes to your keyboard shortcuts, you may set `AreBrowserAcceleratorKeysEnabled` to `FALSE`, which turns off all keys that access browser features, but keeps all basic text-editing and movement shortcuts turned on.</span></span>  

<span data-ttu-id="0be31-241">下表列出了 WebView2 中始终关闭的快捷方式。</span><span class="sxs-lookup"><span data-stu-id="0be31-241">The following table lists the shortcuts that are always turned off in WebView2.</span></span>  <span data-ttu-id="0be31-242">星号 \ (\) 字符指示快捷方式未关闭，但它访问的功能已关闭或不适用于 `*` WebView2。</span><span class="sxs-lookup"><span data-stu-id="0be31-242">An asterisk \(`*`\) character indicates that the shortcut isn't turned off, but the feature it accesses is turned off or doesn't apply to WebView2.</span></span>  

| <span data-ttu-id="0be31-243">操作</span><span class="sxs-lookup"><span data-stu-id="0be31-243">Action</span></span> | <span data-ttu-id="0be31-244">Windows</span><span class="sxs-lookup"><span data-stu-id="0be31-244">Windows</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="0be31-245">添加到</span><span class="sxs-lookup"><span data-stu-id="0be31-245">Add to</span></span> Favorites | `Ctrl`+`D` |  
| <span data-ttu-id="0be31-246">将所有选项卡添加到</span><span class="sxs-lookup"><span data-stu-id="0be31-246">Add All Tabs to</span></span> Favorites | `Ctrl`+`Shift`+`D` |  
| <span data-ttu-id="0be31-247">焦点位置</span><span class="sxs-lookup"><span data-stu-id="0be31-247">Focus Location</span></span> | `Ctrl`+`L, Alt`+`D` |  
| <span data-ttu-id="0be31-248">粘贴并转到</span><span class="sxs-lookup"><span data-stu-id="0be31-248">Paste and Go</span></span> | `Ctrl`+`Shift`+`L` |  
| <span data-ttu-id="0be31-249">打开文件</span><span class="sxs-lookup"><span data-stu-id="0be31-249">Open File</span></span> | `Ctrl`+`O` |  
| Read Aloud `*` | `Ctrl`+`Shift`+`U` |  
| <span data-ttu-id="0be31-250">Web 捕获</span><span class="sxs-lookup"><span data-stu-id="0be31-250">Web Capture</span></span> `*` | `Ctrl`+`Shift`+`S` |  
| <span data-ttu-id="0be31-251">边栏</span><span class="sxs-lookup"><span data-stu-id="0be31-251">Sidebar</span></span> `*` | `Ctrl`+`Shift`+`E` |  
| <span data-ttu-id="0be31-252">保存页面</span><span class="sxs-lookup"><span data-stu-id="0be31-252">Save Page</span></span> | `Ctrl`+`S` |  
| <span data-ttu-id="0be31-253">选择最后一个选项卡</span><span class="sxs-lookup"><span data-stu-id="0be31-253">Select Last Tab</span></span> | `Ctrl`+`9` |  
| <span data-ttu-id="0be31-254">选择下一个选项卡</span><span class="sxs-lookup"><span data-stu-id="0be31-254">Select Next Tab</span></span> | `Ctrl`+`Tab` |  
| <span data-ttu-id="0be31-255">选择上一个选项卡</span><span class="sxs-lookup"><span data-stu-id="0be31-255">Select Previous Tab</span></span> | `Ctrl`+`Shift`+`Tab` |  
| <span data-ttu-id="0be31-256">选择选项卡 \ (1 - 8\) </span><span class="sxs-lookup"><span data-stu-id="0be31-256">Select Tab \(1 - 8\)</span></span> | `Ctrl`+`(1-8)` |  
| <span data-ttu-id="0be31-257">显示 Favorites 栏</span><span class="sxs-lookup"><span data-stu-id="0be31-257">Show Favorites Bar</span></span> `*` | `Ctrl`+`Shift`+`B` |  
| <span data-ttu-id="0be31-258">帮助</span><span class="sxs-lookup"><span data-stu-id="0be31-258">Help</span></span> | `F1` |  
| <span data-ttu-id="0be31-259">焦点下一个窗格</span><span class="sxs-lookup"><span data-stu-id="0be31-259">Focus Next Pane</span></span> `*` | `F6` |  
| <span data-ttu-id="0be31-260">焦点上一个窗格</span><span class="sxs-lookup"><span data-stu-id="0be31-260">Focus Previous Pane</span></span> `*` | `Shift`+`F6` |  
| <span data-ttu-id="0be31-261">项目浏览</span><span class="sxs-lookup"><span data-stu-id="0be31-261">Caret Browsing</span></span> `*` | `F7` |  
| <span data-ttu-id="0be31-262">阅读视图</span><span class="sxs-lookup"><span data-stu-id="0be31-262">Reading View</span></span> `*` | `F9` |  
| <span data-ttu-id="0be31-263">焦点菜单栏</span><span class="sxs-lookup"><span data-stu-id="0be31-263">Focus Menu Bar</span></span> | `F10` |  
| <span data-ttu-id="0be31-264">显示标识菜单</span><span class="sxs-lookup"><span data-stu-id="0be31-264">Show Identity Menu</span></span> `*` | `Ctrl`+`Shift`+`M` |  
| Browser Task Manager `*` | `Shift`+`Escape` |  
| <span data-ttu-id="0be31-265">Edge 反馈</span><span class="sxs-lookup"><span data-stu-id="0be31-265">Edge Feedback</span></span> `*` | `Shift`+`Alt`+`I` |  
| <span data-ttu-id="0be31-266">静音选项卡</span><span class="sxs-lookup"><span data-stu-id="0be31-266">Mute Tab</span></span> `*` | `Ctrl`+`M` |  
| <span data-ttu-id="0be31-267">新建隐身窗口</span><span class="sxs-lookup"><span data-stu-id="0be31-267">New Incognito Window</span></span> | `Ctrl`+`Shift`+`N` |  
| <span data-ttu-id="0be31-268">新建选项卡</span><span class="sxs-lookup"><span data-stu-id="0be31-268">New Tab</span></span> | `Ctrl`+`T` |  
| <span data-ttu-id="0be31-269">新建窗口</span><span class="sxs-lookup"><span data-stu-id="0be31-269">New Window</span></span> | `Ctrl`+`N` |  
| <span data-ttu-id="0be31-270">"还原上次关闭"选项卡</span><span class="sxs-lookup"><span data-stu-id="0be31-270">Restore Last Closed Tab</span></span> | `Ctrl`+`Shift`+`T` |  
| <span data-ttu-id="0be31-271">对焦</span><span class="sxs-lookup"><span data-stu-id="0be31-271">Focus</span></span> Favorites | `Alt`+`Shift`+`B` |  
| <span data-ttu-id="0be31-272">焦点非活动弹出窗口</span><span class="sxs-lookup"><span data-stu-id="0be31-272">Focus Inactive Popup</span></span> | `Alt`+`Shift`+`A` |  
| <span data-ttu-id="0be31-273">焦点搜索</span><span class="sxs-lookup"><span data-stu-id="0be31-273">Focus Search</span></span> | `Ctrl`<span data-ttu-id="0be31-274">+`E`, `Ctrl`+`K`,</span><span class="sxs-lookup"><span data-stu-id="0be31-274">+`E`, `Ctrl`+`K`,</span></span> `Search Key` |  
| <span data-ttu-id="0be31-275">"重复"选项卡</span><span class="sxs-lookup"><span data-stu-id="0be31-275">Duplicate Tab</span></span> | `Ctrl`+`Shift`+`K` |  
| <span data-ttu-id="0be31-276">焦点工具栏</span><span class="sxs-lookup"><span data-stu-id="0be31-276">Focus Toolbar</span></span> `*` | `Alt`+`Shift`+`T` |  
| <span data-ttu-id="0be31-277">主页</span><span class="sxs-lookup"><span data-stu-id="0be31-277">Home</span></span> | `Alt`<span data-ttu-id="0be31-278">+`Home`,</span><span class="sxs-lookup"><span data-stu-id="0be31-278">+`Home`,</span></span> `Browser Home Key` |  
| <span data-ttu-id="0be31-279">显示应用菜单</span><span class="sxs-lookup"><span data-stu-id="0be31-279">Show App Menu</span></span> | `Alt`+`E, Alt`+`F` |  
| <span data-ttu-id="0be31-280">显示</span><span class="sxs-lookup"><span data-stu-id="0be31-280">Show</span></span> Favorites | `Ctrl`+`Shift`+`O` |  
| <span data-ttu-id="0be31-281">显示</span><span class="sxs-lookup"><span data-stu-id="0be31-281">Show</span></span> Downloads | `Ctrl`+`J` |  
| <span data-ttu-id="0be31-282">显示历史记录</span><span class="sxs-lookup"><span data-stu-id="0be31-282">Show History</span></span> | `Ctrl`+`H` |  
| <span data-ttu-id="0be31-283">显示阅读模式栏</span><span class="sxs-lookup"><span data-stu-id="0be31-283">Show Reading Mode Bar</span></span> `*` | `Shift`+`Alt`+`R` |  
| <span data-ttu-id="0be31-284">显示</span><span class="sxs-lookup"><span data-stu-id="0be31-284">Show</span></span> Collections `*` | `Ctrl`+`Shift`+`Y` |  

<span data-ttu-id="0be31-285">以下键盘快捷方式始终关闭，在未处理事件时显示的窗口中 `NewWindowRequested` 除外。</span><span class="sxs-lookup"><span data-stu-id="0be31-285">The following keyboard shortcuts are always turned off, except in windows that display when the `NewWindowRequested` event isn't handled.</span></span>

| <span data-ttu-id="0be31-286">操作</span><span class="sxs-lookup"><span data-stu-id="0be31-286">Action</span></span> | <span data-ttu-id="0be31-287">Windows</span><span class="sxs-lookup"><span data-stu-id="0be31-287">Windows</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="0be31-288">关闭选项卡</span><span class="sxs-lookup"><span data-stu-id="0be31-288">Close Tab</span></span> | `Ctrl`+`W, Ctrl`+`F4` |  
| <span data-ttu-id="0be31-289">关闭窗口</span><span class="sxs-lookup"><span data-stu-id="0be31-289">Close Window</span></span> | `Ctrl`+`Shift`+`W` |  
| <span data-ttu-id="0be31-290">全屏</span><span class="sxs-lookup"><span data-stu-id="0be31-290">Fullscreen</span></span> | `F11` |  

<span data-ttu-id="0be31-291">如果设置为 `AreBrowserAcceleratorKeysEnabled` `FALSE` ，则以下其他键盘快捷方式将关闭。</span><span class="sxs-lookup"><span data-stu-id="0be31-291">If you set `AreBrowserAcceleratorKeysEnabled` to `FALSE`, the following additional keyboard shortcuts are turned off.</span></span>  

| <span data-ttu-id="0be31-292">操作</span><span class="sxs-lookup"><span data-stu-id="0be31-292">Action</span></span> | <span data-ttu-id="0be31-293">Windows</span><span class="sxs-lookup"><span data-stu-id="0be31-293">Windows</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="0be31-294">停止</span><span class="sxs-lookup"><span data-stu-id="0be31-294">Stop</span></span> | `Escape` |  
| <span data-ttu-id="0be31-295">在页面上查找</span><span class="sxs-lookup"><span data-stu-id="0be31-295">Find on Page</span></span> | `Ctrl`+`F` |  
| <span data-ttu-id="0be31-296">查找下一个</span><span class="sxs-lookup"><span data-stu-id="0be31-296">Find Next</span></span> | `Ctrl`+`G` |  
| <span data-ttu-id="0be31-297">查找上一个</span><span class="sxs-lookup"><span data-stu-id="0be31-297">Find Previous</span></span> | `Ctrl`+`Shift`+`G` |  
| <span data-ttu-id="0be31-298">Print</span><span class="sxs-lookup"><span data-stu-id="0be31-298">Print</span></span> | `Ctrl`+`P` |  
| <span data-ttu-id="0be31-299">刷新</span><span class="sxs-lookup"><span data-stu-id="0be31-299">Refresh</span></span> | `Ctrl`<span data-ttu-id="0be31-300">+`R`, `F5`,</span><span class="sxs-lookup"><span data-stu-id="0be31-300">+`R`, `F5`,</span></span> `Reload Key` |  
| <span data-ttu-id="0be31-301">刷新（不含缓存）</span><span class="sxs-lookup"><span data-stu-id="0be31-301">Refresh Without Cache</span></span> | `Ctrl`<span data-ttu-id="0be31-302">+`Shift`+`R`, `Ctrl`+`F5`, `Shift`+`F5`, `Ctrl`+`Refresh`, `Shift`+</span><span class="sxs-lookup"><span data-stu-id="0be31-302">+`Shift`+`R`, `Ctrl`+`F5`, `Shift`+`F5`, `Ctrl`+`Refresh`, `Shift`+</span></span>`Refresh` |  
| <span data-ttu-id="0be31-303">缩小</span><span class="sxs-lookup"><span data-stu-id="0be31-303">Zoom Out</span></span> | `Ctrl`+`-` |  
| <span data-ttu-id="0be31-304">放大</span><span class="sxs-lookup"><span data-stu-id="0be31-304">Zoom In</span></span> | `Ctrl`+`+` |  
| <span data-ttu-id="0be31-305">重置缩放</span><span class="sxs-lookup"><span data-stu-id="0be31-305">Reset Zoom</span></span> | `Ctrl`+`0` |  
| <span data-ttu-id="0be31-306">查找下一个</span><span class="sxs-lookup"><span data-stu-id="0be31-306">Find Next</span></span> | `F3` |  
| <span data-ttu-id="0be31-307">查找上一个</span><span class="sxs-lookup"><span data-stu-id="0be31-307">Find Previous</span></span> | `Shift`+`F3` |  
| <span data-ttu-id="0be31-308">后退</span><span class="sxs-lookup"><span data-stu-id="0be31-308">Back</span></span> | `Alt`+`Left, Browser Back Key` |  
| <span data-ttu-id="0be31-309">前进</span><span class="sxs-lookup"><span data-stu-id="0be31-309">Forward</span></span> | `Alt`<span data-ttu-id="0be31-310">+`Right`,</span><span class="sxs-lookup"><span data-stu-id="0be31-310">+`Right`,</span></span> `Browser Forward Key` |  
| <span data-ttu-id="0be31-311">Print</span><span class="sxs-lookup"><span data-stu-id="0be31-311">Print</span></span> | `Ctrl`+`P` |  
| <span data-ttu-id="0be31-312">打开/关闭 DevTools</span><span class="sxs-lookup"><span data-stu-id="0be31-312">Open / Close DevTools</span></span> | `Ctrl`+`Shift`+`I` |  
| <span data-ttu-id="0be31-313">打开 DevTools 控制台</span><span class="sxs-lookup"><span data-stu-id="0be31-313">Open DevTools Console</span></span> | `Ctrl`+`Shift`+`J` |  
| <span data-ttu-id="0be31-314">打开 DevTools Inspect</span><span class="sxs-lookup"><span data-stu-id="0be31-314">Open DevTools Inspect</span></span> | `Ctrl`+`Shift`+`C` |  

> [!Note] 
> <span data-ttu-id="0be31-315">若要单独自定义任何键，请使用 [AcceleratorKeyPressed][DotnetApiMicrosoftWebWebview2CoreCorewebview2controllerAcceleratorkeypressedViewWebview2Dotnet1077444] 事件。</span><span class="sxs-lookup"><span data-stu-id="0be31-315">To customize any of the keys individually, use the [AcceleratorKeyPressed][DotnetApiMicrosoftWebWebview2CoreCorewebview2controllerAcceleratorkeypressedViewWebview2Dotnet1077444] event.</span></span>  

## <a name="getting-in-touch-with-the-microsoft-edge-webview2-team"></a><span data-ttu-id="0be31-316">与 Microsoft Edge WebView2 团队联系</span><span class="sxs-lookup"><span data-stu-id="0be31-316">Getting in touch with the Microsoft Edge WebView2 team</span></span>  

[!INCLUDE [contact WebView2 team note](../includes/contact-webview-team-note.md)]  

<!-- links -->  

<!--[Webview2ReferenceDownloadApi]: ./download-api.md "download API | Microsoft Docs"  -->  

[DotnetApiMicrosoftWebWebview2CoreCorewebview2controllerAcceleratorkeypressedViewWebview2Dotnet1077444]: /dotnet/api/microsoft.web.webview2.core.corewebview2controller.acceleratorkeypressed?view=webview2-dotnet-1.0.774.44&preserve-view=true "CoreWebView2Controller.AcceleratorKeyPressed 事件|Microsoft Docs"  

[DevtoolsShortcutsIndex]: ../../devtools-guide-chromium/shortcuts/index.md "Microsoft Edge DevTools 键盘快捷方式 | Microsoft Docs"  

[GithubMicrosoftedgeWebview2feedbackIssues308]: https://github.com/MicrosoftEdge/WebView2Feedback/issues/308 "添加对 HTML5 通知 API (#308) |GitHub"  

[PeterExperimentsChromiumCommandLineSwitches]: https://peter.sh/experiments/chromium-command-line-switches "Chromium 命令行开关列表|Peter Beverloo"  
