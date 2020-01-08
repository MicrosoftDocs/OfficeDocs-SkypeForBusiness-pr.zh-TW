---
title: Lync Server 2013： Lync 2013 的新增及變更的設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: New and changed settings for Lync 2013
ms:assetid: bb13789c-7eda-461c-a387-02ea8ca4dabe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205204(v=OCS.15)
ms:contentKeyID: 48185241
ms.date: 12/08/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 675997e815dc80ec173e75ca68358ef23c12f380
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976043"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-and-changed-settings-for-lync-2013"></a><span data-ttu-id="33714-102">Lync 2013 的新增及變更的設定</span><span class="sxs-lookup"><span data-stu-id="33714-102">New and changed settings for Lync 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="33714-103">_**主題上次修改日期：** 2014-12-05_</span><span class="sxs-lookup"><span data-stu-id="33714-103">_**Topic Last Modified:** 2014-12-05_</span></span>

<span data-ttu-id="33714-104">本主題討論與用戶端管理直接相關的 Lync Server 管理命令介面 Cmdlet 變更。</span><span class="sxs-lookup"><span data-stu-id="33714-104">This topic discusses changes to Lync Server Management Shell cmdlets that relate directly to client management.</span></span> <span data-ttu-id="33714-105">Lync Server 2013 會引入數個新參數，並 deprecates 可透過其他方式設定的功能的參數。</span><span class="sxs-lookup"><span data-stu-id="33714-105">Lync Server 2013 introduces several new parameters, and deprecates parameters for features that can be configured through other means.</span></span>

<div>

## <a name="new-client-management-parameters"></a><span data-ttu-id="33714-106">新的用戶端管理參數</span><span class="sxs-lookup"><span data-stu-id="33714-106">New Client Management Parameters</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="33714-107">新增功能</span><span class="sxs-lookup"><span data-stu-id="33714-107">New</span></span></th>
<th><span data-ttu-id="33714-108">Lync Server 管理命令介面 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="33714-108">Lync Server Management Shell Cmdlet</span></span></th>
<th><span data-ttu-id="33714-109">描述</span><span class="sxs-lookup"><span data-stu-id="33714-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="33714-110">TracingLevel</span><span class="sxs-lookup"><span data-stu-id="33714-110">TracingLevel</span></span></p></td>
<td><p><span data-ttu-id="33714-111">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="33714-111">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="33714-112">當設定為 True 時，會在 Lync 啟用軟體追蹤;當設為 False 時，軟體追蹤將停用。</span><span class="sxs-lookup"><span data-stu-id="33714-112">When set to True, software tracing will be enabled in Lync; when set to False, software tracing will be disabled.</span></span> <span data-ttu-id="33714-113">軟體追蹤涉及對程式所執行的所有專案（包括追蹤 API 呼叫）進行詳細記錄。</span><span class="sxs-lookup"><span data-stu-id="33714-113">Software tracing involves keeping a detailed record of everything that a program does (including tracking API calls).</span></span> <span data-ttu-id="33714-114">追蹤功能對開發人員和應用程式支援人員而言是很有用的。這個設定相當於通訊伺服器 2007 R2 群組原則設定&quot;開啟 Communicator 追蹤功能。&quot;這些設定如下所示：</span><span class="sxs-lookup"><span data-stu-id="33714-114">Tracing is mostly useful to developers and to application support personnel.This setting is equivalent to the Communications Server 2007 R2 Group Policy setting &quot;Turn on tracing for Communicator.&quot; The settings are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="33714-115">關閉 = 已停用追蹤，且使用者無法變更此設定。</span><span class="sxs-lookup"><span data-stu-id="33714-115">Off = Tracing is disabled and the user cannot change this setting.</span></span></p></li>
<li><p><span data-ttu-id="33714-116">Light = 執行最小追蹤，使用者無法變更此設定。</span><span class="sxs-lookup"><span data-stu-id="33714-116">Light = Minimal tracing is performed, and the user cannot change this setting.</span></span></p></li>
<li><p><span data-ttu-id="33714-117">開啟 = 進行詳細追蹤，使用者無法變更此設定。</span><span class="sxs-lookup"><span data-stu-id="33714-117">On = Verbose tracing is performed, and the user cannot change this setting.</span></span></p></li>
</ul>
<p><span data-ttu-id="33714-118">根據預設，TracingLevel 會設定為 null 值。</span><span class="sxs-lookup"><span data-stu-id="33714-118">By default TracingLevel is set to a null value.</span></span> <span data-ttu-id="33714-119">這表示會執行最少的追蹤，但使用者可以啟用或停用這種最小追蹤。</span><span class="sxs-lookup"><span data-stu-id="33714-119">That means that minimal tracing is performed, but the user can enable or disable this minimal tracing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33714-120">EnableMediaRedirection</span><span class="sxs-lookup"><span data-stu-id="33714-120">EnableMediaRedirection</span></span></p></td>
<td><p><span data-ttu-id="33714-121">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="33714-121">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="33714-122">當設定為 True （$True）時，會讓音訊和影片資料流程與其他網路流量分開，進而讓用戶端裝置在本機進行音訊與視頻解碼及解碼。</span><span class="sxs-lookup"><span data-stu-id="33714-122">When set to True ($True) allows audio and video streams to be separated from other network traffic, In turn, this allows client devices to do encoding and decoding of audio and video locally.</span></span> <span data-ttu-id="33714-123">媒體重新導向通常會產生較低的頻寬使用量、較高的伺服器可伸縮性，以及與類似裝置（例如裝置遠端處理或編解碼器壓縮）相比更加最佳的使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="33714-123">Media redirection typically results in lower bandwidth usage, higher server scalability, and a more-optimal user experience compared to similar techniques such as device remoting or codec compression.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33714-124">AllowLargeMeetings</span><span class="sxs-lookup"><span data-stu-id="33714-124">AllowLargeMeetings</span></span></p></td>
<td><p><span data-ttu-id="33714-125">CsConferencing</span><span class="sxs-lookup"><span data-stu-id="33714-125">CsConferencing</span></span></p></td>
<td><p><span data-ttu-id="33714-126">當設定為 True 時，所有 Lync 會議都會被&quot;視為大型會議。&quot;使用大型會議時，除了預設傳送的會議名單大小之外，還會針對傳送給參與者的通知數量加上限制。</span><span class="sxs-lookup"><span data-stu-id="33714-126">When set to True, all Lync Meetings are treated as &quot;large meetings.&quot; With a large meeting, restrictions are placed on the number of notifications that are sent to participants, in addition to the size of the meeting roster that is transmitted by default.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33714-127">DisablePowerPointAnnotations</span><span class="sxs-lookup"><span data-stu-id="33714-127">DisablePowerPointAnnotations</span></span></p></td>
<td><p><span data-ttu-id="33714-128">CsConferencing</span><span class="sxs-lookup"><span data-stu-id="33714-128">CsConferencing</span></span></p></td>
<td><p><span data-ttu-id="33714-129">當設定為 True （$True）時，使用者將無法在會議中使用 PowerPoint 投影片上新增批註。</span><span class="sxs-lookup"><span data-stu-id="33714-129">When set to True ($True) users won’t be able to add annotations to PowerPoint slides used in a conference.</span></span> <span data-ttu-id="33714-130">不過（視 AllowAnnotations 屬性的值而定），使用者仍可存取其他 whiteboarding 功能。</span><span class="sxs-lookup"><span data-stu-id="33714-130">However (depending on the value of the AllowAnnotations property), users will still have access to other whiteboarding features.</span></span> <span data-ttu-id="33714-131">預設值為 False，表示允許使用 PowerPoint 標注。</span><span class="sxs-lookup"><span data-stu-id="33714-131">The default value is False, meaning that PowerPoint annotations are allowed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33714-132">AllowSharedNotes</span><span class="sxs-lookup"><span data-stu-id="33714-132">AllowSharedNotes</span></span></p></td>
<td><p><span data-ttu-id="33714-133">CsConferencing</span><span class="sxs-lookup"><span data-stu-id="33714-133">CsConferencing</span></span></p></td>
<td><p><span data-ttu-id="33714-134">當設定為 True （預設值）時，連結至會議的任何開啟的 OneNote 筆記本都會自動更新，其中包含會議參與者的相關資訊，以及在會議期間共用之內容的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="33714-134">When set to True (the default value) any open OneNote notebooks linked to the conference will automatically be updated with information such as conference participants and details about content shared during the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33714-135">EnableInviteCustomization</span><span class="sxs-lookup"><span data-stu-id="33714-135">EnableInviteCustomization</span></span></p></td>
<td><p><span data-ttu-id="33714-136">CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="33714-136">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="33714-137">與其他新的 CsMeetingConfiguration 參數搭配使用，來自訂 Lync 2013 的線上會議增益集所產生的會議邀請。</span><span class="sxs-lookup"><span data-stu-id="33714-137">Used along with the other new CsMeetingConfiguration parameters to customize the meeting invitations generated by the Online Meeting Add-in for Lync 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33714-138">LogoURL</span><span class="sxs-lookup"><span data-stu-id="33714-138">LogoURL</span></span></p></td>
<td><p><span data-ttu-id="33714-139">CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="33714-139">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="33714-140">將貴組織的標誌新增至由 Lync 2013 的線上會議增益集所產生的所有邀請。</span><span class="sxs-lookup"><span data-stu-id="33714-140">Adds your organization’s logo to all invitations generated by the Online Meeting Add-in for Lync 2013.</span></span> <span data-ttu-id="33714-141">您可以指定 GIF 或 JPG 影像的 URL。</span><span class="sxs-lookup"><span data-stu-id="33714-141">You specify the URL of a GIF or JPG image.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33714-142">HelpURL</span><span class="sxs-lookup"><span data-stu-id="33714-142">HelpURL</span></span></p></td>
<td><p><span data-ttu-id="33714-143">CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="33714-143">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="33714-144">將貴組織的說明或支援 URL 新增到由 Lync 2013 的線上會議增益集所產生的所有邀請。</span><span class="sxs-lookup"><span data-stu-id="33714-144">Adds your organization’s help or support URL to all invitations generated by the Online Meeting Add-in for Lync 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33714-145">LegalURL</span><span class="sxs-lookup"><span data-stu-id="33714-145">LegalURL</span></span></p></td>
<td><p><span data-ttu-id="33714-146">CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="33714-146">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="33714-147">在 Lync 2013 的線上會議增益集所產生的所有邀請中，新增法律文字或免責聲明文字。</span><span class="sxs-lookup"><span data-stu-id="33714-147">Adds legal text or disclaimer text to all invitations generated by the Online Meeting Add-in for Lync 2013.</span></span> <span data-ttu-id="33714-148">您可以指定文字位置的 URL。</span><span class="sxs-lookup"><span data-stu-id="33714-148">You specify the URL for the location of the text.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33714-149">CustomFooterText</span><span class="sxs-lookup"><span data-stu-id="33714-149">CustomFooterText</span></span></p></td>
<td><p><span data-ttu-id="33714-150">CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="33714-150">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="33714-151">將自訂頁尾新增至由 Lync 2013 的線上會議增益集所產生的所有邀請。</span><span class="sxs-lookup"><span data-stu-id="33714-151">Adds a custom footer to all invitations generated by the Online Meeting Add-in for Lync 2013.</span></span> <span data-ttu-id="33714-152">您可以指定自訂頁尾文字位置的 URL。</span><span class="sxs-lookup"><span data-stu-id="33714-152">You specify the URL for the location of the custom footer text.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="deprecated-client-management-parameters"></a><span data-ttu-id="33714-153">過時的用戶端管理參數</span><span class="sxs-lookup"><span data-stu-id="33714-153">Deprecated Client Management Parameters</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="33714-154">參數</span><span class="sxs-lookup"><span data-stu-id="33714-154">Parameter</span></span></th>
<th><span data-ttu-id="33714-155">Lync Server 管理命令介面 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="33714-155">Lync Server Management Shell Cmdlet</span></span></th>
<th><span data-ttu-id="33714-156">描述</span><span class="sxs-lookup"><span data-stu-id="33714-156">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="33714-157">CustomizedHelpUrl</span><span class="sxs-lookup"><span data-stu-id="33714-157">CustomizedHelpUrl</span></span></p></td>
<td><p><span data-ttu-id="33714-158">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="33714-158">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="33714-159">此參數已棄用，可與 Lync Server 2013 搭配使用。</span><span class="sxs-lookup"><span data-stu-id="33714-159">This parameter has been deprecated for use with Lync Server 2013.</span></span> <span data-ttu-id="33714-160">與 EnableEnterpriseCustomizedHelp 搭配使用時，此參數會讓組織指定 URL，以便在使用者按一下 Lync 中的 [說明] 功能表時，自訂的 [說明] 會顯示。</span><span class="sxs-lookup"><span data-stu-id="33714-160">When used in conjunction with EnableEnterpriseCustomizedHelp, this parameter enabled an organization to specify a URL so that when users clicked the Help menu in Lync, customized help would display.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33714-161">EnableEnterpriseCustomizedHelp</span><span class="sxs-lookup"><span data-stu-id="33714-161">EnableEnterpriseCustomizedHelp</span></span></p></td>
<td><p><span data-ttu-id="33714-162">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="33714-162">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="33714-163">此參數已棄用，可與 Lync Server 2013 搭配使用。</span><span class="sxs-lookup"><span data-stu-id="33714-163">This parameter has been deprecated for use with Lync Server 2013.</span></span> <span data-ttu-id="33714-164">與 CustomizedHelpUrl 搭配使用時，此參數可讓組織顯示自訂的說明。</span><span class="sxs-lookup"><span data-stu-id="33714-164">When used in conjunction with CustomizedHelpUrl, this parameter enabled organizations to display customized help.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33714-165">EnableSQMData</span><span class="sxs-lookup"><span data-stu-id="33714-165">EnableSQMData</span></span></p></td>
<td><p><span data-ttu-id="33714-166">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="33714-166">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="33714-167">已在 Lync Server 2013 中移除 Set CSClientPolicy Cmdlet 的 EnableSQMData 參數。</span><span class="sxs-lookup"><span data-stu-id="33714-167">The EnableSQMData parameter of the Set-CSClientPolicy cmdlet has been removed in Lync Server 2013.</span></span> <span data-ttu-id="33714-168">相反地，您可以使用軟體品質管制（SQM）資料的共用群組原則設定來決定 [Lync 用戶端一般選項] 頁面中的 [客戶經驗改進] 選項的使用者介面：</span><span class="sxs-lookup"><span data-stu-id="33714-168">Instead, you can use the shared Group Policy setting for Software Quality Management (SQM) data to determine the user interface for the Customer Experience Improvement option in the Lync client General options page:</span></span></p>
<p><span data-ttu-id="33714-169">HKEY_CURRENT_USER \Software\Policies\Microsoft\Office\Common\QMEnable</span><span class="sxs-lookup"><span data-stu-id="33714-169">HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\Common\QMEnable</span></span></p>
<p><span data-ttu-id="33714-170">相對值</span><span class="sxs-lookup"><span data-stu-id="33714-170">Values:</span></span></p>
<p><span data-ttu-id="33714-171">1 = 顯示並選取核取方塊（使用者可以清除核取方塊）</span><span class="sxs-lookup"><span data-stu-id="33714-171">1 = Display and select the check box (the user can clear the check box)</span></span></p>
<p><span data-ttu-id="33714-172">0 = 關閉並停用核取方塊（使用者無法覆寫）</span><span class="sxs-lookup"><span data-stu-id="33714-172">0 = Turn off and disable the check box (user can't override)</span></span></p>
<p><span data-ttu-id="33714-173">Null = 此值是由 Office 設定決定，且會顯示使用者設定的核取方塊，讓使用者選擇</span><span class="sxs-lookup"><span data-stu-id="33714-173">Null = The value is determined by Office setup, and the check box is displayed for users to set as they choose</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33714-174">AllowExchangeContactStore</span><span class="sxs-lookup"><span data-stu-id="33714-174">AllowExchangeContactStore</span></span></p></td>
<td><p><span data-ttu-id="33714-175">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="33714-175">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="33714-176">此參數已移除。</span><span class="sxs-lookup"><span data-stu-id="33714-176">This parameter has been removed.</span></span> <span data-ttu-id="33714-177">相反地，當您部署 Lync Server 2013 併發布拓撲時，預設會啟用所有使用者的「整合連絡人存放區」。</span><span class="sxs-lookup"><span data-stu-id="33714-177">Instead, when you deploy Lync Server 2013 and publish the topology, unified contact store is enabled for all users by default.</span></span> <span data-ttu-id="33714-178">這表示所有使用者的連絡人都會保留在 Exchange 中，且可在 Lync、Outlook 和 Outlook Web Access 中取得。</span><span class="sxs-lookup"><span data-stu-id="33714-178">This means that all a user’s contacts are kept in Exchange and are available in Lync, Outlook, and Outlook Web Access.</span></span> <span data-ttu-id="33714-179">您可以使用 CsUserServicesPolicy Cmdlet 來自訂哪些使用者可以使用 [整合] 連絡人存放區。</span><span class="sxs-lookup"><span data-stu-id="33714-179">You can use the Set-CsUserServicesPolicy cmdlet to customize which users have unified contact store available.</span></span> <span data-ttu-id="33714-180">您可以將使用者全域性、依網站、由租使用者，或由個人或一組人員來啟用。</span><span class="sxs-lookup"><span data-stu-id="33714-180">You can enable users globally, by site, by tenant, or by individuals or groups of individuals.</span></span> <span data-ttu-id="33714-181">如需詳細資訊，請參閱<a href="lync-server-2013-enable-users-for-unified-contact-store.md">在 Lync Server 2013 中為整合連絡人存放區啟用使用者</a>。</span><span class="sxs-lookup"><span data-stu-id="33714-181">For details, see <a href="lync-server-2013-enable-users-for-unified-contact-store.md">Enable users for unified contact store in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33714-182">MAPIPollInterval</span><span class="sxs-lookup"><span data-stu-id="33714-182">MAPIPollInterval</span></span></p></td>
<td><p><span data-ttu-id="33714-183">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="33714-183">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="33714-184">Lync 2013 不會使用這個參數。</span><span class="sxs-lookup"><span data-stu-id="33714-184">This parameter is not used by Lync 2013.</span></span> <span data-ttu-id="33714-185">在前一個版本中，此參數指定用戶端從 Exchange 公用資料夾中檢索到 MAPI 資料的頻率</span><span class="sxs-lookup"><span data-stu-id="33714-185">In previous releases, this parameter specified how often the client retrieved MAPI data from Exchange public folders</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33714-186">DisableICE</span><span class="sxs-lookup"><span data-stu-id="33714-186">DisableICE</span></span></p></td>
<td><p><span data-ttu-id="33714-187">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="33714-187">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="33714-188">在 Lync 2013 中已棄用此參數。</span><span class="sxs-lookup"><span data-stu-id="33714-188">This parameter was deprecated in Lync 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

