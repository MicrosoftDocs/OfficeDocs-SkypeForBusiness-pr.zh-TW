---
title: Lync Server 2013： Lync 2013 的新增和變更設定
description: Lync Server 2013： Lync 2013 的新增和變更設定。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New and changed settings for Lync 2013
ms:assetid: bb13789c-7eda-461c-a387-02ea8ca4dabe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205204(v=OCS.15)
ms:contentKeyID: 48185241
ms.date: 12/08/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1bf744e1bae774904733390ec624be523ad32bc1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561389"
---
# <a name="new-and-changed-settings-for-lync-2013"></a><span data-ttu-id="cae00-103">Lync 2013 的新增及變更的設定</span><span class="sxs-lookup"><span data-stu-id="cae00-103">New and changed settings for Lync 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cae00-104">_**主題上次修改日期：** 2014-12-05_</span><span class="sxs-lookup"><span data-stu-id="cae00-104">_**Topic Last Modified:** 2014-12-05_</span></span>

<span data-ttu-id="cae00-105">本主題討論與直接與用戶端管理相關之 Lync Server 管理命令介面 Cmdlet 的變更。</span><span class="sxs-lookup"><span data-stu-id="cae00-105">This topic discusses changes to Lync Server Management Shell cmdlets that relate directly to client management.</span></span> <span data-ttu-id="cae00-106">Lync Server 2013 引進數個新參數，並 deprecates 可透過其他方式設定之功能的參數。</span><span class="sxs-lookup"><span data-stu-id="cae00-106">Lync Server 2013 introduces several new parameters, and deprecates parameters for features that can be configured through other means.</span></span>

<div>

## <a name="new-client-management-parameters"></a><span data-ttu-id="cae00-107">新的用戶端管理參數</span><span class="sxs-lookup"><span data-stu-id="cae00-107">New Client Management Parameters</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cae00-108">新增</span><span class="sxs-lookup"><span data-stu-id="cae00-108">New</span></span></th>
<th><span data-ttu-id="cae00-109">Lync Server 管理命令介面 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="cae00-109">Lync Server Management Shell Cmdlet</span></span></th>
<th><span data-ttu-id="cae00-110">描述</span><span class="sxs-lookup"><span data-stu-id="cae00-110">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cae00-111">TracingLevel</span><span class="sxs-lookup"><span data-stu-id="cae00-111">TracingLevel</span></span></p></td>
<td><p><span data-ttu-id="cae00-112">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="cae00-112">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="cae00-113">設為 True 時，會在 Lync 啟用軟體追蹤;設為 False 時，軟體追蹤將會停用。</span><span class="sxs-lookup"><span data-stu-id="cae00-113">When set to True, software tracing will be enabled in Lync; when set to False, software tracing will be disabled.</span></span> <span data-ttu-id="cae00-114">軟體追蹤包含保留程式所進行之所有事項的詳細記錄 (包括追蹤 API 呼叫)。</span><span class="sxs-lookup"><span data-stu-id="cae00-114">Software tracing involves keeping a detailed record of everything that a program does (including tracking API calls).</span></span> <span data-ttu-id="cae00-115">追蹤功能主要適用于開發人員和應用程式支援人員。此設定相當於 [通訊伺服器 2007 R2 群組原則] 設定 [ &quot; 開啟 Communicator 追蹤]。 &quot; 設定如下：</span><span class="sxs-lookup"><span data-stu-id="cae00-115">Tracing is mostly useful to developers and to application support personnel.This setting is equivalent to the Communications Server 2007 R2 Group Policy setting &quot;Turn on tracing for Communicator.&quot; The settings are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="cae00-116">Off = 停用追蹤，使用者無法變更此設定。</span><span class="sxs-lookup"><span data-stu-id="cae00-116">Off = Tracing is disabled and the user cannot change this setting.</span></span></p></li>
<li><p><span data-ttu-id="cae00-117">淺色 = 執行最小追蹤，使用者無法變更此設定。</span><span class="sxs-lookup"><span data-stu-id="cae00-117">Light = Minimal tracing is performed, and the user cannot change this setting.</span></span></p></li>
<li><p><span data-ttu-id="cae00-118">On = 執行詳細追蹤，使用者無法變更此設定。</span><span class="sxs-lookup"><span data-stu-id="cae00-118">On = Verbose tracing is performed, and the user cannot change this setting.</span></span></p></li>
</ul>
<p><span data-ttu-id="cae00-119">依預設，TracingLevel 會設為 null 值。</span><span class="sxs-lookup"><span data-stu-id="cae00-119">By default TracingLevel is set to a null value.</span></span> <span data-ttu-id="cae00-120">這表示執行最小追蹤，但使用者可以啟用或停用這種最小追蹤。</span><span class="sxs-lookup"><span data-stu-id="cae00-120">That means that minimal tracing is performed, but the user can enable or disable this minimal tracing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cae00-121">EnableMediaRedirection</span><span class="sxs-lookup"><span data-stu-id="cae00-121">EnableMediaRedirection</span></span></p></td>
<td><p><span data-ttu-id="cae00-122">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="cae00-122">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="cae00-123">設為 True 時 ($True) 允許音訊和影片的資料流程與其他網路流量分開，這樣就能讓用戶端裝置在本機進行音訊和影片的編碼和解碼。</span><span class="sxs-lookup"><span data-stu-id="cae00-123">When set to True ($True) allows audio and video streams to be separated from other network traffic, In turn, this allows client devices to do encoding and decoding of audio and video locally.</span></span> <span data-ttu-id="cae00-124">與裝置遠端處理或轉碼器壓縮等類似的技術相較，媒體重新導向通常會使頻寬使用較低、伺服器擴充性較高，且使用者經驗較佳。</span><span class="sxs-lookup"><span data-stu-id="cae00-124">Media redirection typically results in lower bandwidth usage, higher server scalability, and a more-optimal user experience compared to similar techniques such as device remoting or codec compression.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cae00-125">AllowLargeMeetings</span><span class="sxs-lookup"><span data-stu-id="cae00-125">AllowLargeMeetings</span></span></p></td>
<td><p><span data-ttu-id="cae00-126">CsConferencing</span><span class="sxs-lookup"><span data-stu-id="cae00-126">CsConferencing</span></span></p></td>
<td><p><span data-ttu-id="cae00-127">設為 True 時，會將所有 Lync 會議視為 &quot; 大型會議。 &quot; 使用大型會議時，除了預設傳輸的會議名單大小之外，也會限制傳送給參與者的通知數目。</span><span class="sxs-lookup"><span data-stu-id="cae00-127">When set to True, all Lync Meetings are treated as &quot;large meetings.&quot; With a large meeting, restrictions are placed on the number of notifications that are sent to participants, in addition to the size of the meeting roster that is transmitted by default.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cae00-128">DisablePowerPointAnnotations</span><span class="sxs-lookup"><span data-stu-id="cae00-128">DisablePowerPointAnnotations</span></span></p></td>
<td><p><span data-ttu-id="cae00-129">CsConferencing</span><span class="sxs-lookup"><span data-stu-id="cae00-129">CsConferencing</span></span></p></td>
<td><p><span data-ttu-id="cae00-130">設為 True 時 ($True) 使用者將無法將批註新增至會議中所用 PowerPoint 的投影片。</span><span class="sxs-lookup"><span data-stu-id="cae00-130">When set to True ($True) users won’t be able to add annotations to PowerPoint slides used in a conference.</span></span> <span data-ttu-id="cae00-131">不過 (取決於 AllowAnnotations 屬性的值) ，使用者仍可存取其他的白板功能。</span><span class="sxs-lookup"><span data-stu-id="cae00-131">However (depending on the value of the AllowAnnotations property), users will still have access to other whiteboarding features.</span></span> <span data-ttu-id="cae00-132">預設值為 False，表示允許使用 PowerPoint 批註。</span><span class="sxs-lookup"><span data-stu-id="cae00-132">The default value is False, meaning that PowerPoint annotations are allowed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cae00-133">AllowSharedNotes</span><span class="sxs-lookup"><span data-stu-id="cae00-133">AllowSharedNotes</span></span></p></td>
<td><p><span data-ttu-id="cae00-134">CsConferencing</span><span class="sxs-lookup"><span data-stu-id="cae00-134">CsConferencing</span></span></p></td>
<td><p><span data-ttu-id="cae00-135">設為 True 時 (預設值) 會自動更新連結至會議的任何開啟 OneNote 筆記本的資訊，例如會議參與者的資訊，以及在會議期間共用之內容的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="cae00-135">When set to True (the default value) any open OneNote notebooks linked to the conference will automatically be updated with information such as conference participants and details about content shared during the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cae00-136">EnableInviteCustomization</span><span class="sxs-lookup"><span data-stu-id="cae00-136">EnableInviteCustomization</span></span></p></td>
<td><p><span data-ttu-id="cae00-137">CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="cae00-137">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="cae00-138">與其他新的 CsMeetingConfiguration 參數一起使用，以自訂 Lync 2013 之線上會議增益集所產生的會議邀請。</span><span class="sxs-lookup"><span data-stu-id="cae00-138">Used along with the other new CsMeetingConfiguration parameters to customize the meeting invitations generated by the Online Meeting Add-in for Lync 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cae00-139">LogoURL</span><span class="sxs-lookup"><span data-stu-id="cae00-139">LogoURL</span></span></p></td>
<td><p><span data-ttu-id="cae00-140">CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="cae00-140">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="cae00-141">將組織的標誌新增至所有由 Lync 2013 之線上會議增益集所產生的所有邀請。</span><span class="sxs-lookup"><span data-stu-id="cae00-141">Adds your organization’s logo to all invitations generated by the Online Meeting Add-in for Lync 2013.</span></span> <span data-ttu-id="cae00-142">您可以指定 GIF 或 JPG 圖像的 URL。</span><span class="sxs-lookup"><span data-stu-id="cae00-142">You specify the URL of a GIF or JPG image.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cae00-143">HelpURL</span><span class="sxs-lookup"><span data-stu-id="cae00-143">HelpURL</span></span></p></td>
<td><p><span data-ttu-id="cae00-144">CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="cae00-144">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="cae00-145">將您組織的說明或支援 URL 新增至 Lync 2013 之線上會議增益集所產生的所有邀請。</span><span class="sxs-lookup"><span data-stu-id="cae00-145">Adds your organization’s help or support URL to all invitations generated by the Online Meeting Add-in for Lync 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cae00-146">LegalURL</span><span class="sxs-lookup"><span data-stu-id="cae00-146">LegalURL</span></span></p></td>
<td><p><span data-ttu-id="cae00-147">CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="cae00-147">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="cae00-148">針對 Lync 2013 的線上會議增益集所產生的所有邀請，新增法律文字或免責聲明文字。</span><span class="sxs-lookup"><span data-stu-id="cae00-148">Adds legal text or disclaimer text to all invitations generated by the Online Meeting Add-in for Lync 2013.</span></span> <span data-ttu-id="cae00-149">您可以指定文字位置的 URL。</span><span class="sxs-lookup"><span data-stu-id="cae00-149">You specify the URL for the location of the text.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cae00-150">CustomFooterText</span><span class="sxs-lookup"><span data-stu-id="cae00-150">CustomFooterText</span></span></p></td>
<td><p><span data-ttu-id="cae00-151">CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="cae00-151">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="cae00-152">會將自訂的頁尾新增至由 Lync 2013 之線上會議增益集所產生的所有邀請。</span><span class="sxs-lookup"><span data-stu-id="cae00-152">Adds a custom footer to all invitations generated by the Online Meeting Add-in for Lync 2013.</span></span> <span data-ttu-id="cae00-153">您可以指定自訂頁腳文字位置的 URL。</span><span class="sxs-lookup"><span data-stu-id="cae00-153">You specify the URL for the location of the custom footer text.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="deprecated-client-management-parameters"></a><span data-ttu-id="cae00-154">已被取代的用戶端管理參數</span><span class="sxs-lookup"><span data-stu-id="cae00-154">Deprecated Client Management Parameters</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cae00-155">參數</span><span class="sxs-lookup"><span data-stu-id="cae00-155">Parameter</span></span></th>
<th><span data-ttu-id="cae00-156">Lync Server 管理命令介面 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="cae00-156">Lync Server Management Shell Cmdlet</span></span></th>
<th><span data-ttu-id="cae00-157">描述</span><span class="sxs-lookup"><span data-stu-id="cae00-157">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cae00-158">CustomizedHelpUrl</span><span class="sxs-lookup"><span data-stu-id="cae00-158">CustomizedHelpUrl</span></span></p></td>
<td><p><span data-ttu-id="cae00-159">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="cae00-159">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="cae00-160">此參數已被取代，無法搭配 Lync Server 2013 使用。</span><span class="sxs-lookup"><span data-stu-id="cae00-160">This parameter has been deprecated for use with Lync Server 2013.</span></span> <span data-ttu-id="cae00-161">與 EnableEnterpriseCustomizedHelp 搭配使用時，此參數會讓組織指定 URL，這樣當使用者按一下 Lync 中的 [說明] 功能表時，就會顯示自訂的 [說明]。</span><span class="sxs-lookup"><span data-stu-id="cae00-161">When used in conjunction with EnableEnterpriseCustomizedHelp, this parameter enabled an organization to specify a URL so that when users clicked the Help menu in Lync, customized help would display.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cae00-162">EnableEnterpriseCustomizedHelp</span><span class="sxs-lookup"><span data-stu-id="cae00-162">EnableEnterpriseCustomizedHelp</span></span></p></td>
<td><p><span data-ttu-id="cae00-163">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="cae00-163">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="cae00-164">此參數已被取代，無法搭配 Lync Server 2013 使用。</span><span class="sxs-lookup"><span data-stu-id="cae00-164">This parameter has been deprecated for use with Lync Server 2013.</span></span> <span data-ttu-id="cae00-165">與 CustomizedHelpUrl 搭配使用時，此參數會讓組織顯示自訂的 [說明]。</span><span class="sxs-lookup"><span data-stu-id="cae00-165">When used in conjunction with CustomizedHelpUrl, this parameter enabled organizations to display customized help.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cae00-166">EnableSQMData</span><span class="sxs-lookup"><span data-stu-id="cae00-166">EnableSQMData</span></span></p></td>
<td><p><span data-ttu-id="cae00-167">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="cae00-167">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="cae00-168">已在 Lync Server 2013 中移除 Set-CSClientPolicy Cmdlet 的 EnableSQMData 參數。</span><span class="sxs-lookup"><span data-stu-id="cae00-168">The EnableSQMData parameter of the Set-CSClientPolicy cmdlet has been removed in Lync Server 2013.</span></span> <span data-ttu-id="cae00-169">相反地，您可以使用「軟體品質管制」的共用群組原則設定來 (SQM) 資料，以判斷「Lync 用戶端一般選項」頁面中的「客戶經驗改進」選項的使用者介面：</span><span class="sxs-lookup"><span data-stu-id="cae00-169">Instead, you can use the shared Group Policy setting for Software Quality Management (SQM) data to determine the user interface for the Customer Experience Improvement option in the Lync client General options page:</span></span></p>
<p><span data-ttu-id="cae00-170">HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\Common\QMEnable</span><span class="sxs-lookup"><span data-stu-id="cae00-170">HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\Common\QMEnable</span></span></p>
<p><span data-ttu-id="cae00-171">值：</span><span class="sxs-lookup"><span data-stu-id="cae00-171">Values:</span></span></p>
<p><span data-ttu-id="cae00-172">1 = 顯示並選取此核取方塊 (使用者可以清除核取方塊) </span><span class="sxs-lookup"><span data-stu-id="cae00-172">1 = Display and select the check box (the user can clear the check box)</span></span></p>
<p><span data-ttu-id="cae00-173">0 = 關閉並停用此核取方塊 (使用者無法覆寫) </span><span class="sxs-lookup"><span data-stu-id="cae00-173">0 = Turn off and disable the check box (user can't override)</span></span></p>
<p><span data-ttu-id="cae00-174">Null = 此值是由 Office 安裝程式所決定，而且會顯示一個核取方塊，讓使用者將其設定為選擇</span><span class="sxs-lookup"><span data-stu-id="cae00-174">Null = The value is determined by Office setup, and the check box is displayed for users to set as they choose</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cae00-175">AllowExchangeContactStore</span><span class="sxs-lookup"><span data-stu-id="cae00-175">AllowExchangeContactStore</span></span></p></td>
<td><p><span data-ttu-id="cae00-176">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="cae00-176">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="cae00-177">此參數已被移除。</span><span class="sxs-lookup"><span data-stu-id="cae00-177">This parameter has been removed.</span></span> <span data-ttu-id="cae00-178">相反地，當您部署 Lync Server 2013 併發行拓撲時，預設會為所有使用者啟用整合連絡人存放區。</span><span class="sxs-lookup"><span data-stu-id="cae00-178">Instead, when you deploy Lync Server 2013 and publish the topology, unified contact store is enabled for all users by default.</span></span> <span data-ttu-id="cae00-179">這表示，所有使用者的連絡人都會保留在 Exchange 中，且可用於 Lync、Outlook 和 Outlook Web Access。</span><span class="sxs-lookup"><span data-stu-id="cae00-179">This means that all a user’s contacts are kept in Exchange and are available in Lync, Outlook, and Outlook Web Access.</span></span> <span data-ttu-id="cae00-180">您可以使用 Set-CsUserServicesPolicy Cmdlet 來自訂哪些使用者擁有整合的連絡人存放區。</span><span class="sxs-lookup"><span data-stu-id="cae00-180">You can use the Set-CsUserServicesPolicy cmdlet to customize which users have unified contact store available.</span></span> <span data-ttu-id="cae00-181">您可以依租使用者或個別個人或個別群組的方式啟用使用者。</span><span class="sxs-lookup"><span data-stu-id="cae00-181">You can enable users globally, by site, by tenant, or by individuals or groups of individuals.</span></span> <span data-ttu-id="cae00-182">如需詳細資訊，請參閱 <a href="lync-server-2013-enable-users-for-unified-contact-store.md">在 Lync Server 2013 中啟用整合連絡人存放區的使用者</a>。</span><span class="sxs-lookup"><span data-stu-id="cae00-182">For details, see <a href="lync-server-2013-enable-users-for-unified-contact-store.md">Enable users for unified contact store in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cae00-183">MAPIPollInterval</span><span class="sxs-lookup"><span data-stu-id="cae00-183">MAPIPollInterval</span></span></p></td>
<td><p><span data-ttu-id="cae00-184">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="cae00-184">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="cae00-185">Lync 2013 不會使用此參數。</span><span class="sxs-lookup"><span data-stu-id="cae00-185">This parameter is not used by Lync 2013.</span></span> <span data-ttu-id="cae00-186">在舊版本中，此參數指定用戶端從 Exchange 公用資料夾中檢索 MAPI 資料的頻率</span><span class="sxs-lookup"><span data-stu-id="cae00-186">In previous releases, this parameter specified how often the client retrieved MAPI data from Exchange public folders</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cae00-187">DisableICE</span><span class="sxs-lookup"><span data-stu-id="cae00-187">DisableICE</span></span></p></td>
<td><p><span data-ttu-id="cae00-188">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="cae00-188">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="cae00-189">此參數在 Lync 2013 中已被取代。</span><span class="sxs-lookup"><span data-stu-id="cae00-189">This parameter was deprecated in Lync 2013.</span></span></p></td>
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

