---
title: Lync 2013 的 Lync Server 2013： 新增及變更設定
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
ms.openlocfilehash: ba26f3175f461f0cdc68924b20c1413bf13a2b41
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42128116"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="new-and-changed-settings-for-lync-2013"></a><span data-ttu-id="6e5e1-102">Lync 2013 的新增及變更設定</span><span class="sxs-lookup"><span data-stu-id="6e5e1-102">New and changed settings for Lync 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6e5e1-103">_**上次修改主題：** 2014年-12-05_</span><span class="sxs-lookup"><span data-stu-id="6e5e1-103">_**Topic Last Modified:** 2014-12-05_</span></span>

<span data-ttu-id="6e5e1-104">本主題討論變更至與用戶端管理直接相關的 Lync Server 管理命令介面指令程式。</span><span class="sxs-lookup"><span data-stu-id="6e5e1-104">This topic discusses changes to Lync Server Management Shell cmdlets that relate directly to client management.</span></span> <span data-ttu-id="6e5e1-105">Lync Server 2013 引進數個新參數，並 deprecates 參數可以透過其他方式進行設定的功能。</span><span class="sxs-lookup"><span data-stu-id="6e5e1-105">Lync Server 2013 introduces several new parameters, and deprecates parameters for features that can be configured through other means.</span></span>

<div>

## <a name="new-client-management-parameters"></a><span data-ttu-id="6e5e1-106">新的用戶端管理參數</span><span class="sxs-lookup"><span data-stu-id="6e5e1-106">New Client Management Parameters</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6e5e1-107">新增</span><span class="sxs-lookup"><span data-stu-id="6e5e1-107">New</span></span></th>
<th><span data-ttu-id="6e5e1-108">Lync Server 管理命令介面指令程式</span><span class="sxs-lookup"><span data-stu-id="6e5e1-108">Lync Server Management Shell Cmdlet</span></span></th>
<th><span data-ttu-id="6e5e1-109">描述</span><span class="sxs-lookup"><span data-stu-id="6e5e1-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6e5e1-110">TracingLevel</span><span class="sxs-lookup"><span data-stu-id="6e5e1-110">TracingLevel</span></span></p></td>
<td><p><span data-ttu-id="6e5e1-111">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="6e5e1-111">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="6e5e1-112">當您將會設為 True，軟體追蹤啟用在 Lync;當設為 False，軟體追蹤將會停用。</span><span class="sxs-lookup"><span data-stu-id="6e5e1-112">When set to True, software tracing will be enabled in Lync; when set to False, software tracing will be disabled.</span></span> <span data-ttu-id="6e5e1-113">軟體追蹤包含保留程式所進行之所有事項的詳細記錄 (包括追蹤 API 呼叫)。</span><span class="sxs-lookup"><span data-stu-id="6e5e1-113">Software tracing involves keeping a detailed record of everything that a program does (including tracking API calls).</span></span> <span data-ttu-id="6e5e1-114">追蹤是大部分有用的開發人員和應用程式的支援人員。此設定相當於 [Communications Server 2007 R2 群組原則設定&quot;開啟 Communicator 追蹤。&quot; ，如下所示的設定包括：</span><span class="sxs-lookup"><span data-stu-id="6e5e1-114">Tracing is mostly useful to developers and to application support personnel.This setting is equivalent to the Communications Server 2007 R2 Group Policy setting &quot;Turn on tracing for Communicator.&quot; The settings are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="6e5e1-115">關 = 停用追蹤，使用者無法變更此設定。</span><span class="sxs-lookup"><span data-stu-id="6e5e1-115">Off = Tracing is disabled and the user cannot change this setting.</span></span></p></li>
<li><p><span data-ttu-id="6e5e1-116">輕 = 執行最基本的追蹤是，且使用者無法變更此設定。</span><span class="sxs-lookup"><span data-stu-id="6e5e1-116">Light = Minimal tracing is performed, and the user cannot change this setting.</span></span></p></li>
<li><p><span data-ttu-id="6e5e1-117">開 = Verbose 追蹤已執行，且使用者無法變更此設定。</span><span class="sxs-lookup"><span data-stu-id="6e5e1-117">On = Verbose tracing is performed, and the user cannot change this setting.</span></span></p></li>
</ul>
<p><span data-ttu-id="6e5e1-118">根據預設 TracingLevel 設為 null 值。</span><span class="sxs-lookup"><span data-stu-id="6e5e1-118">By default TracingLevel is set to a null value.</span></span> <span data-ttu-id="6e5e1-119">這表示會執行最基本的追蹤，但使用者可以啟用或停用這個最基本的追蹤。</span><span class="sxs-lookup"><span data-stu-id="6e5e1-119">That means that minimal tracing is performed, but the user can enable or disable this minimal tracing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e5e1-120">EnableMediaRedirection</span><span class="sxs-lookup"><span data-stu-id="6e5e1-120">EnableMediaRedirection</span></span></p></td>
<td><p><span data-ttu-id="6e5e1-121">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="6e5e1-121">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="6e5e1-122">當設為 True ($True) 可讓與其他的網路流量，依序分開的音訊和視訊資料流時，這可讓用戶端裝置進行編碼和解碼音訊及視訊在本機上。</span><span class="sxs-lookup"><span data-stu-id="6e5e1-122">When set to True ($True) allows audio and video streams to be separated from other network traffic, In turn, this allows client devices to do encoding and decoding of audio and video locally.</span></span> <span data-ttu-id="6e5e1-123">與裝置遠端處理或轉碼器壓縮等類似的技術相較，媒體重新導向通常會使頻寬使用較低、伺服器擴充性較高，且使用者經驗較佳。</span><span class="sxs-lookup"><span data-stu-id="6e5e1-123">Media redirection typically results in lower bandwidth usage, higher server scalability, and a more-optimal user experience compared to similar techniques such as device remoting or codec compression.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e5e1-124">AllowLargeMeetings</span><span class="sxs-lookup"><span data-stu-id="6e5e1-124">AllowLargeMeetings</span></span></p></td>
<td><p><span data-ttu-id="6e5e1-125">CsConferencing</span><span class="sxs-lookup"><span data-stu-id="6e5e1-125">CsConferencing</span></span></p></td>
<td><p><span data-ttu-id="6e5e1-126">設為 True 時，所有 Lync Meeting 都視為&quot;大型會議。&quot;大型會議，以限制置於此外預設傳輸的會議名冊大小傳送給參與者的通知數目。</span><span class="sxs-lookup"><span data-stu-id="6e5e1-126">When set to True, all Lync Meetings are treated as &quot;large meetings.&quot; With a large meeting, restrictions are placed on the number of notifications that are sent to participants, in addition to the size of the meeting roster that is transmitted by default.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e5e1-127">DisablePowerPointAnnotations</span><span class="sxs-lookup"><span data-stu-id="6e5e1-127">DisablePowerPointAnnotations</span></span></p></td>
<td><p><span data-ttu-id="6e5e1-128">CsConferencing</span><span class="sxs-lookup"><span data-stu-id="6e5e1-128">CsConferencing</span></span></p></td>
<td><p><span data-ttu-id="6e5e1-129">當設為 True ($True) 使用者將無法將註解新增至 PowerPoint 投影片在會議中使用。</span><span class="sxs-lookup"><span data-stu-id="6e5e1-129">When set to True ($True) users won’t be able to add annotations to PowerPoint slides used in a conference.</span></span> <span data-ttu-id="6e5e1-130">不過，（根據 AllowAnnotations 屬性的值），使用者仍會有其他白板功能的存取權。</span><span class="sxs-lookup"><span data-stu-id="6e5e1-130">However (depending on the value of the AllowAnnotations property), users will still have access to other whiteboarding features.</span></span> <span data-ttu-id="6e5e1-131">預設值為 False，這表示可允許 PowerPoint 註釋。</span><span class="sxs-lookup"><span data-stu-id="6e5e1-131">The default value is False, meaning that PowerPoint annotations are allowed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e5e1-132">AllowSharedNotes</span><span class="sxs-lookup"><span data-stu-id="6e5e1-132">AllowSharedNotes</span></span></p></td>
<td><p><span data-ttu-id="6e5e1-133">CsConferencing</span><span class="sxs-lookup"><span data-stu-id="6e5e1-133">CsConferencing</span></span></p></td>
<td><p><span data-ttu-id="6e5e1-134">當設為 True （預設值） 在任何開啟連結到會議的 OneNote 筆記本會自動更新會議參與者和詳細資料等在會議期間共用的內容相關的資訊。</span><span class="sxs-lookup"><span data-stu-id="6e5e1-134">When set to True (the default value) any open OneNote notebooks linked to the conference will automatically be updated with information such as conference participants and details about content shared during the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e5e1-135">EnableInviteCustomization</span><span class="sxs-lookup"><span data-stu-id="6e5e1-135">EnableInviteCustomization</span></span></p></td>
<td><p><span data-ttu-id="6e5e1-136">CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="6e5e1-136">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="6e5e1-137">與其他新 CsMeetingConfiguration 參數一起使用自訂的線上會議增益集 Lync 2013 所產生的會議邀請。</span><span class="sxs-lookup"><span data-stu-id="6e5e1-137">Used along with the other new CsMeetingConfiguration parameters to customize the meeting invitations generated by the Online Meeting Add-in for Lync 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e5e1-138">LogoURL</span><span class="sxs-lookup"><span data-stu-id="6e5e1-138">LogoURL</span></span></p></td>
<td><p><span data-ttu-id="6e5e1-139">CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="6e5e1-139">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="6e5e1-140">將貴組織的商標新增至產生的線上會議增益集 Lync 2013 的所有邀請。</span><span class="sxs-lookup"><span data-stu-id="6e5e1-140">Adds your organization’s logo to all invitations generated by the Online Meeting Add-in for Lync 2013.</span></span> <span data-ttu-id="6e5e1-141">您指定 GIF 或 JPG 影像 URL。</span><span class="sxs-lookup"><span data-stu-id="6e5e1-141">You specify the URL of a GIF or JPG image.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e5e1-142">HelpURL</span><span class="sxs-lookup"><span data-stu-id="6e5e1-142">HelpURL</span></span></p></td>
<td><p><span data-ttu-id="6e5e1-143">CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="6e5e1-143">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="6e5e1-144">將貴組織的說明或支援 URL 新增至產生的線上會議增益集 Lync 2013 的所有邀請。</span><span class="sxs-lookup"><span data-stu-id="6e5e1-144">Adds your organization’s help or support URL to all invitations generated by the Online Meeting Add-in for Lync 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e5e1-145">LegalURL</span><span class="sxs-lookup"><span data-stu-id="6e5e1-145">LegalURL</span></span></p></td>
<td><p><span data-ttu-id="6e5e1-146">CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="6e5e1-146">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="6e5e1-147">將法律或免責聲明文字新增至產生的線上會議增益集 Lync 2013 的所有邀請。</span><span class="sxs-lookup"><span data-stu-id="6e5e1-147">Adds legal text or disclaimer text to all invitations generated by the Online Meeting Add-in for Lync 2013.</span></span> <span data-ttu-id="6e5e1-148">您指定文字的位置的 URL。</span><span class="sxs-lookup"><span data-stu-id="6e5e1-148">You specify the URL for the location of the text.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e5e1-149">CustomFooterText</span><span class="sxs-lookup"><span data-stu-id="6e5e1-149">CustomFooterText</span></span></p></td>
<td><p><span data-ttu-id="6e5e1-150">CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="6e5e1-150">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="6e5e1-151">將自訂的頁尾新增至產生的線上會議增益集 Lync 2013 的所有邀請。</span><span class="sxs-lookup"><span data-stu-id="6e5e1-151">Adds a custom footer to all invitations generated by the Online Meeting Add-in for Lync 2013.</span></span> <span data-ttu-id="6e5e1-152">您指定的自訂頁尾文字的位置的 URL。</span><span class="sxs-lookup"><span data-stu-id="6e5e1-152">You specify the URL for the location of the custom footer text.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="deprecated-client-management-parameters"></a><span data-ttu-id="6e5e1-153">已被取代的用戶端管理參數</span><span class="sxs-lookup"><span data-stu-id="6e5e1-153">Deprecated Client Management Parameters</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6e5e1-154">參數</span><span class="sxs-lookup"><span data-stu-id="6e5e1-154">Parameter</span></span></th>
<th><span data-ttu-id="6e5e1-155">Lync Server 管理命令介面指令程式</span><span class="sxs-lookup"><span data-stu-id="6e5e1-155">Lync Server Management Shell Cmdlet</span></span></th>
<th><span data-ttu-id="6e5e1-156">描述</span><span class="sxs-lookup"><span data-stu-id="6e5e1-156">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6e5e1-157">CustomizedHelpUrl</span><span class="sxs-lookup"><span data-stu-id="6e5e1-157">CustomizedHelpUrl</span></span></p></td>
<td><p><span data-ttu-id="6e5e1-158">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="6e5e1-158">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="6e5e1-159">搭配 Lync Server 2013 已淘汰此參數。</span><span class="sxs-lookup"><span data-stu-id="6e5e1-159">This parameter has been deprecated for use with Lync Server 2013.</span></span> <span data-ttu-id="6e5e1-160">中 enableenterprisecustomizedhelp 設搭配使用時，此參數會啟用組織，以指定的 URL，這樣當使用者按下 Lync 中的 [說明] 功能表，會顯示自訂的說明。</span><span class="sxs-lookup"><span data-stu-id="6e5e1-160">When used in conjunction with EnableEnterpriseCustomizedHelp, this parameter enabled an organization to specify a URL so that when users clicked the Help menu in Lync, customized help would display.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e5e1-161">Enableenterprisecustomizedhelp 設</span><span class="sxs-lookup"><span data-stu-id="6e5e1-161">EnableEnterpriseCustomizedHelp</span></span></p></td>
<td><p><span data-ttu-id="6e5e1-162">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="6e5e1-162">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="6e5e1-163">搭配 Lync Server 2013 已淘汰此參數。</span><span class="sxs-lookup"><span data-stu-id="6e5e1-163">This parameter has been deprecated for use with Lync Server 2013.</span></span> <span data-ttu-id="6e5e1-164">中 CustomizedHelpUrl 搭配使用時，此參數會啟用組織若要顯示自訂的說明。</span><span class="sxs-lookup"><span data-stu-id="6e5e1-164">When used in conjunction with CustomizedHelpUrl, this parameter enabled organizations to display customized help.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e5e1-165">EnableSQMData</span><span class="sxs-lookup"><span data-stu-id="6e5e1-165">EnableSQMData</span></span></p></td>
<td><p><span data-ttu-id="6e5e1-166">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="6e5e1-166">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="6e5e1-167">Lync Server 2013 中已移除 Set-csclientpolicy cmdlet 的 EnableSQMData 參數。</span><span class="sxs-lookup"><span data-stu-id="6e5e1-167">The EnableSQMData parameter of the Set-CSClientPolicy cmdlet has been removed in Lync Server 2013.</span></span> <span data-ttu-id="6e5e1-168">相反地，您可以使用軟體品質管理 (SQM) 資料共用的群組原則的設定來決定在 Lync 用戶端一般選項] 頁面的 [客戶經驗改進] 選項的使用者介面：</span><span class="sxs-lookup"><span data-stu-id="6e5e1-168">Instead, you can use the shared Group Policy setting for Software Quality Management (SQM) data to determine the user interface for the Customer Experience Improvement option in the Lync client General options page:</span></span></p>
<p><span data-ttu-id="6e5e1-169">HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\Common\QMEnable</span><span class="sxs-lookup"><span data-stu-id="6e5e1-169">HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\Common\QMEnable</span></span></p>
<p><span data-ttu-id="6e5e1-170">值：</span><span class="sxs-lookup"><span data-stu-id="6e5e1-170">Values:</span></span></p>
<p><span data-ttu-id="6e5e1-171">1 = 顯示並選取核取方塊 （使用者可以清除核取方塊）</span><span class="sxs-lookup"><span data-stu-id="6e5e1-171">1 = Display and select the check box (the user can clear the check box)</span></span></p>
<p><span data-ttu-id="6e5e1-172">0 = 關閉並停用] 核取方塊 （使用者無法覆寫）</span><span class="sxs-lookup"><span data-stu-id="6e5e1-172">0 = Turn off and disable the check box (user can't override)</span></span></p>
<p><span data-ttu-id="6e5e1-173">Null = 值取決於 Office 安裝程式，並且] 核取方塊會顯示使用者設為他們選擇</span><span class="sxs-lookup"><span data-stu-id="6e5e1-173">Null = The value is determined by Office setup, and the check box is displayed for users to set as they choose</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e5e1-174">AllowExchangeContactStore</span><span class="sxs-lookup"><span data-stu-id="6e5e1-174">AllowExchangeContactStore</span></span></p></td>
<td><p><span data-ttu-id="6e5e1-175">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="6e5e1-175">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="6e5e1-176">此參數已被移除。</span><span class="sxs-lookup"><span data-stu-id="6e5e1-176">This parameter has been removed.</span></span> <span data-ttu-id="6e5e1-177">相反地，當您部署 Lync Server 2013，並發行拓撲，整合連絡人存放區預設會啟用所有使用者。</span><span class="sxs-lookup"><span data-stu-id="6e5e1-177">Instead, when you deploy Lync Server 2013 and publish the topology, unified contact store is enabled for all users by default.</span></span> <span data-ttu-id="6e5e1-178">這表示所有使用者的連絡人會保留在 Exchange 和 Lync、 Outlook 和 Outlook Web Access 中提供。</span><span class="sxs-lookup"><span data-stu-id="6e5e1-178">This means that all a user’s contacts are kept in Exchange and are available in Lync, Outlook, and Outlook Web Access.</span></span> <span data-ttu-id="6e5e1-179">您可用於自訂哪些使用者具有整合連絡人存放區提供 Set-csuserservicespolicy cmdlet。</span><span class="sxs-lookup"><span data-stu-id="6e5e1-179">You can use the Set-CsUserServicesPolicy cmdlet to customize which users have unified contact store available.</span></span> <span data-ttu-id="6e5e1-180">您可以啟用全域、 網站、 租用戶，或藉由個人或群組的個人的使用者。</span><span class="sxs-lookup"><span data-stu-id="6e5e1-180">You can enable users globally, by site, by tenant, or by individuals or groups of individuals.</span></span> <span data-ttu-id="6e5e1-181">如需詳細資訊，請參閱<a href="lync-server-2013-enable-users-for-unified-contact-store.md">啟用使用者的 Lync Server 2013 中整合連絡人存放區</a>。</span><span class="sxs-lookup"><span data-stu-id="6e5e1-181">For details, see <a href="lync-server-2013-enable-users-for-unified-contact-store.md">Enable users for unified contact store in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e5e1-182">MAPIPollInterval</span><span class="sxs-lookup"><span data-stu-id="6e5e1-182">MAPIPollInterval</span></span></p></td>
<td><p><span data-ttu-id="6e5e1-183">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="6e5e1-183">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="6e5e1-184">Lync 2013 不使用此參數。</span><span class="sxs-lookup"><span data-stu-id="6e5e1-184">This parameter is not used by Lync 2013.</span></span> <span data-ttu-id="6e5e1-185">在先前版本中，此參數會指定用戶端從 Exchange 公用資料夾擷取 MAPI 資料的頻率</span><span class="sxs-lookup"><span data-stu-id="6e5e1-185">In previous releases, this parameter specified how often the client retrieved MAPI data from Exchange public folders</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e5e1-186">DisableICE</span><span class="sxs-lookup"><span data-stu-id="6e5e1-186">DisableICE</span></span></p></td>
<td><p><span data-ttu-id="6e5e1-187">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="6e5e1-187">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="6e5e1-188">Lync 2013 中，此參數已被取代。</span><span class="sxs-lookup"><span data-stu-id="6e5e1-188">This parameter was deprecated in Lync 2013.</span></span></p></td>
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

