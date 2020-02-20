---
title: 使用 Lync 整合的協力廠商共同作業應用程式
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Integrating a third-party collaboration application with Lync
ms:assetid: 00b9312c-b0c8-4f79-8b76-05b2d820e197
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398068(v=OCS.15)
ms:contentKeyID: 48183224
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ae021735f5fec25cfaba625bd61460e9f58abb4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145412"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="integrating-a-third-party-collaboration-application-with-lync-server-2013"></a><span data-ttu-id="4858a-102">整合的協力廠商共同作業應用程式與 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4858a-102">Integrating a third-party collaboration application with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4858a-103">_**上次修改主題：** 2013年-02-20 個_</span><span class="sxs-lookup"><span data-stu-id="4858a-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="4858a-104">您可以新增至登錄的應用程式的相關資訊，與任何協力廠商線上共同作業應用程式整合 Lync 2013。</span><span class="sxs-lookup"><span data-stu-id="4858a-104">You can integrate Lync 2013 with any third-party online collaboration application by adding information about the application to the registry.</span></span> <span data-ttu-id="4858a-105">您可以使用 Lync 2013 啟動裝載於內部伺服器、 網際網路為基礎的服務，或兩者上的資料會議工作階段。</span><span class="sxs-lookup"><span data-stu-id="4858a-105">You can use Lync 2013 to start data conferencing sessions hosted on an in-house server, an Internet-based service, or both.</span></span> <span data-ttu-id="4858a-106">您可以從 [連絡人清單] 或從現有的立即訊息、語音或視訊工作階段，啟動共同作業或資料會議工作階段。</span><span class="sxs-lookup"><span data-stu-id="4858a-106">The collaboration or data conferencing session can be started from the Contacts list or from an existing instant messaging, voice, or video session.</span></span> <span data-ttu-id="4858a-107">Lync 2013 僅作為啟動應用程式的工具。</span><span class="sxs-lookup"><span data-stu-id="4858a-107">Lync 2013 acts only as the vehicle for starting the application.</span></span> <span data-ttu-id="4858a-108">開始在線上共同作業工作階段之後，保持使用中任何現有的 Lync 2013 交談。</span><span class="sxs-lookup"><span data-stu-id="4858a-108">Any existing Lync 2013 conversations remain active after the online collaboration session has begun.</span></span>

<span data-ttu-id="4858a-109">下列各節說明如何將 Lync 2013 整合與網際網路與伺服器共同作業應用程式。</span><span class="sxs-lookup"><span data-stu-id="4858a-109">The following sections describe how to integrate Lync 2013 with Internet-based and server-based collaboration applications.</span></span>

<div>

## <a name="integrating-an-internet-based-collaboration-application-with-lync-2013"></a><span data-ttu-id="4858a-110">整合網際網路共同作業應用程式與 Lync 2013</span><span class="sxs-lookup"><span data-stu-id="4858a-110">Integrating an Internet-Based Collaboration Application with Lync 2013</span></span>

<span data-ttu-id="4858a-111">基本上，與協力廠商共同作業應用程式整合相關的步驟如下：</span><span class="sxs-lookup"><span data-stu-id="4858a-111">Generally, the steps involved in integrating a third-party collaboration application are as follows:</span></span>

1.  <span data-ttu-id="4858a-112">應用程式的相關資訊會新增到登錄中。</span><span class="sxs-lookup"><span data-stu-id="4858a-112">Information about the application is added to the registry.</span></span>

2.  <span data-ttu-id="4858a-113">組合管理登入 Lync 2013，並選取資料的共用與共同作業的連絡人。</span><span class="sxs-lookup"><span data-stu-id="4858a-113">The organizer signs in to Lync 2013 and selects contacts for data sharing and collaboration.</span></span> <span data-ttu-id="4858a-114">或者，召集人可能已經在交談中，並決定新增資料會議。</span><span class="sxs-lookup"><span data-stu-id="4858a-114">Or, the organizer may already be in a conversation and decide to add data conferencing.</span></span>

3.  <span data-ttu-id="4858a-115">Lync 2013 會讀取登錄、 啟動共同作業應用程式，然後傳送自訂 SIP 訊息 — appINVITE — 給選取的參與者。</span><span class="sxs-lookup"><span data-stu-id="4858a-115">Lync 2013 reads the registry, starts the collaboration application, and then sends a custom SIP message—an appINVITE—to the selected participants.</span></span>

4.  <span data-ttu-id="4858a-116">參與者會接受邀請，並在每個人的電腦上啟動共同作業應用程式。</span><span class="sxs-lookup"><span data-stu-id="4858a-116">Participants accept the invitation, and the collaboration application is started on each person’s computer.</span></span> <span data-ttu-id="4858a-117">Lync 2013 會使用登錄來判斷哪些共同作業應用程式使用，而且再啟動該應用程式所使用的參數包含在 appINVITE 郵件。</span><span class="sxs-lookup"><span data-stu-id="4858a-117">Lync 2013 uses the registry to determine which collaboration application to use, and then starts that application by using the parameters included in the appINVITE message.</span></span>

<span data-ttu-id="4858a-118">下表說明與 Lync 2013 整合網際網路共同作業應用程式所需的登錄項目。</span><span class="sxs-lookup"><span data-stu-id="4858a-118">The following table describes the registry entries required to integrate an Internet-based collaboration application with Lync 2013.</span></span> <span data-ttu-id="4858a-119">這些項目會放在登錄中的下列位置：</span><span class="sxs-lookup"><span data-stu-id="4858a-119">These entries are placed in the registry in the following location:</span></span>

  - <span data-ttu-id="4858a-120">HKEY\_本機\_機器\\軟體\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\參數</span><span class="sxs-lookup"><span data-stu-id="4858a-120">HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters</span></span>

### <a name="registry-entries-for-an-internet-based-collaboration-application"></a><span data-ttu-id="4858a-121">網際網路共同作業應用程式的登錄項目</span><span class="sxs-lookup"><span data-stu-id="4858a-121">Registry Entries for an Internet-based Collaboration Application</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4858a-122">名稱</span><span class="sxs-lookup"><span data-stu-id="4858a-122">Name</span></span></th>
<th><span data-ttu-id="4858a-123">Type</span><span class="sxs-lookup"><span data-stu-id="4858a-123">Type</span></span></th>
<th><span data-ttu-id="4858a-124">Data (資料)</span><span class="sxs-lookup"><span data-stu-id="4858a-124">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4858a-125">名稱</span><span class="sxs-lookup"><span data-stu-id="4858a-125">Name</span></span></p></td>
<td><p><span data-ttu-id="4858a-126">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="4858a-126">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="4858a-127">Lync 2013 功能表應用程式名稱。</span><span class="sxs-lookup"><span data-stu-id="4858a-127">The application name for Lync 2013 menus.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4858a-128">SmallIcon</span><span class="sxs-lookup"><span data-stu-id="4858a-128">SmallIcon</span></span></p></td>
<td><p><span data-ttu-id="4858a-129">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="4858a-129">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="4858a-130">16 像素 x 16 像素圖示 (BMP 或 PNG) 的路徑。</span><span class="sxs-lookup"><span data-stu-id="4858a-130">Path to 16-pixel x 16-pixel icon, BMP or PNG.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4858a-131">路徑</span><span class="sxs-lookup"><span data-stu-id="4858a-131">Path</span></span></p></td>
<td><p><span data-ttu-id="4858a-132">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="4858a-132">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="4858a-133">啟動線上共同作業應用程式的參與者路徑。</span><span class="sxs-lookup"><span data-stu-id="4858a-133">Participant path for starting the online collaboration application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4858a-134">OriginatorPath</span><span class="sxs-lookup"><span data-stu-id="4858a-134">OriginatorPath</span></span></p></td>
<td><p><span data-ttu-id="4858a-135">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="4858a-135">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="4858a-136">啟動線上共同作業應用程式的召集人路徑。</span><span class="sxs-lookup"><span data-stu-id="4858a-136">Organizer path for starting the online collaboration application.</span></span> <span data-ttu-id="4858a-137">這個路徑可以包含一或多個自訂參數，做為 Parameters 子機碼中定義的參數。</span><span class="sxs-lookup"><span data-stu-id="4858a-137">This path can contain one or more custom parameters as defined in the Parameters subkey.</span></span> <span data-ttu-id="4858a-138">例如，<code>https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&amp;role=present&amp;pw=%param3%</code></span><span class="sxs-lookup"><span data-stu-id="4858a-138">For example, <code>https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&amp;role=present&amp;pw=%param3%</code></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4858a-139">SessionType</span><span class="sxs-lookup"><span data-stu-id="4858a-139">SessionType</span></span></p></td>
<td><p><span data-ttu-id="4858a-140">DWORD</span><span class="sxs-lookup"><span data-stu-id="4858a-140">DWORD</span></span></p></td>
<td><p><span data-ttu-id="4858a-p106">0 = 本機工作階段。在本機電腦上啟動應用程式。</span><span class="sxs-lookup"><span data-stu-id="4858a-p106">0 = Local session. The application is started on the local computer.</span></span></p>
<p><span data-ttu-id="4858a-143">1 = 兩方工作階段 (預設)。</span><span class="sxs-lookup"><span data-stu-id="4858a-143">1 = Two-party session (default).</span></span> <span data-ttu-id="4858a-144">Lync 2013 啟動在本機上，在應用程式，然後將系統通知傳送給其他使用者。</span><span class="sxs-lookup"><span data-stu-id="4858a-144">Lync 2013 starts the application locally, and then sends a system notification to the other user.</span></span> <span data-ttu-id="4858a-145">另一位使用者按一下通知並在他們的電腦上啟動指定的應用程式。</span><span class="sxs-lookup"><span data-stu-id="4858a-145">The other user clicks the notification and starts the specified application on their computer.</span></span></p>
<p><span data-ttu-id="4858a-146">2 = 多方工作階段。</span><span class="sxs-lookup"><span data-stu-id="4858a-146">2 = Multiparty session.</span></span> <span data-ttu-id="4858a-147">Lync 2013 啟動在本機上，在應用程式，然後將系統通知傳送給其他使用者，提示使用者在自己的電腦上啟動指定的應用程式。</span><span class="sxs-lookup"><span data-stu-id="4858a-147">Lync 2013 starts the application locally, and then sends system notifications to the other users, prompting them to start the specified application on their own computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4858a-148">ExensibleMenu</span><span class="sxs-lookup"><span data-stu-id="4858a-148">ExensibleMenu</span></span></p></td>
<td><p><span data-ttu-id="4858a-149">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="4858a-149">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="4858a-p109">會出現這個命令的功能表清單 (以分號分隔)。可能的值有：</span><span class="sxs-lookup"><span data-stu-id="4858a-p109">A list of the menus where this command will appear, separated by semi-colons. Possible values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="4858a-152">MainWindowActions</span><span class="sxs-lookup"><span data-stu-id="4858a-152">MainWindowActions</span></span></p></li>
<li><p><span data-ttu-id="4858a-153">MainWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="4858a-153">MainWindowRightClick</span></span></p></li>
<li><p><span data-ttu-id="4858a-154">ConversationWindowActions</span><span class="sxs-lookup"><span data-stu-id="4858a-154">ConversationWindowActions</span></span></p></li>
<li><p><span data-ttu-id="4858a-155">ConversationWindowButton</span><span class="sxs-lookup"><span data-stu-id="4858a-155">ConversationWindowButton</span></span></p></li>
<li><p><span data-ttu-id="4858a-156">ConversationWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="4858a-156">ConversationWindowRightClick</span></span></p></li>
</ul>
<p><span data-ttu-id="4858a-157">如果沒有定義 ExtensibleMenu ，會使用 MainWindowRightClick 和 ConversationWindowActions 的預設值。</span><span class="sxs-lookup"><span data-stu-id="4858a-157">If ExtensibleMenu is not defined, the default values of MainWindowRightClick and ConversationWindowActions are used.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4858a-158">下表說明參數的登錄項目。</span><span class="sxs-lookup"><span data-stu-id="4858a-158">The following table describes the registry entries for parameters.</span></span> <span data-ttu-id="4858a-159">這些項目是在 HKEY\_目前\_使用者\\軟體\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\參數。</span><span class="sxs-lookup"><span data-stu-id="4858a-159">These entries are place at HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters.</span></span>

### <a name="registry-entries-for-an-internet-based-collaboration-application"></a><span data-ttu-id="4858a-160">網際網路共同作業應用程式的登錄項目</span><span class="sxs-lookup"><span data-stu-id="4858a-160">Registry Entries for an Internet-based Collaboration Application</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4858a-161">名稱</span><span class="sxs-lookup"><span data-stu-id="4858a-161">Name</span></span></th>
<th><span data-ttu-id="4858a-162">Type</span><span class="sxs-lookup"><span data-stu-id="4858a-162">Type</span></span></th>
<th><span data-ttu-id="4858a-163">Data (資料)</span><span class="sxs-lookup"><span data-stu-id="4858a-163">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4858a-164">Param1</span><span class="sxs-lookup"><span data-stu-id="4858a-164">Param1</span></span></p></td>
<td><p><span data-ttu-id="4858a-165">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="4858a-165">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="4858a-166">語彙基元化格式中使用 (<code>%Parm1%</code>) 將使用者特定的值新增到 OriginatorPath 登錄機碼。</span><span class="sxs-lookup"><span data-stu-id="4858a-166">Used in tokenized format (<code>%Parm1%</code>) to add user-specific values to the OriginatorPath registry key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4858a-167">Param2</span><span class="sxs-lookup"><span data-stu-id="4858a-167">Param2</span></span></p></td>
<td><p><span data-ttu-id="4858a-168">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="4858a-168">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="4858a-169">請參閱 Param1。</span><span class="sxs-lookup"><span data-stu-id="4858a-169">See Param1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4858a-170">Param3</span><span class="sxs-lookup"><span data-stu-id="4858a-170">Param3</span></span></p></td>
<td><p><span data-ttu-id="4858a-171">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="4858a-171">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="4858a-172">請參閱 Param1。</span><span class="sxs-lookup"><span data-stu-id="4858a-172">See Param1.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4858a-173">下列範例會登錄設定與 Lync 2013 整合 ADatum Collaboration Client:</span><span class="sxs-lookup"><span data-stu-id="4858a-173">The following example registry settings integrate ADatum Collaboration Client with Lync 2013:</span></span>

    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager]
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager\Apps]
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager\Apps\{C3F6E17A-855F-44a0-B90D-C0B92D38E5F1}]
    "Path"="https://meetingservice.adatum.com/cc/%param1%/meet/%param2%"
    "OriginatorPath"="https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&role=present&pw=%param3%"
    "SessionType"=dword:00000002
    "ApplicationType"=dword:00000001
    "LiveServerIntegration"=dword:00000000
    "Name"="ADatum Online Collaboration Service"
    "Extensiblemenu"="MainWindowActions;MainWindowRightClick;ConversationWindowActions;ConversationWindowRightClick"
    
    [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\SessionManager]
    [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\SessionManager\Apps]
    [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\SessionManager\Apps\Parameters]
    [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\SessionManager\Apps\Parameters\{C3F6E17A-855F-44a0-B90D-C0B92D38E5F1}]
    "Param1"="meetserv"
    "Param2"="admin"
    "Param3"="abcdefg123"

</div>

<div>

## <a name="integrating-a-server-based-collaboration-application-with-lync-2013"></a><span data-ttu-id="4858a-174">整合伺服器共同作業應用程式與 Lync 2013</span><span class="sxs-lookup"><span data-stu-id="4858a-174">Integrating a Server-Based Collaboration Application with Lync 2013</span></span>

<span data-ttu-id="4858a-175">若要新增命令以啟動 Lync 2013 內從伺服器型的共同作業應用程式的設定很類似所描述的前一個] 區段中，整合網際網路型的共同作業應用程式與 Lync 2013。</span><span class="sxs-lookup"><span data-stu-id="4858a-175">The settings to add commands for starting a server-based collaboration application from within Lync 2013 are similar to those described in the previous section, Integrating an Internet-Based Collaboration Application with Lync 2013.</span></span> <span data-ttu-id="4858a-176">不過，不需要 OriginatorPath，而且有些值已經變更。</span><span class="sxs-lookup"><span data-stu-id="4858a-176">However, the OriginatorPath is not required, and some values are changed.</span></span> <span data-ttu-id="4858a-177">登錄項目會放在下列位置：</span><span class="sxs-lookup"><span data-stu-id="4858a-177">Registry entries are placed in the following location:</span></span>

  - <span data-ttu-id="4858a-178">HKEY\_本機\_機器\\軟體\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\參數</span><span class="sxs-lookup"><span data-stu-id="4858a-178">HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters</span></span>

### <a name="registry-entries-for-a-server-based-collaboration-application"></a><span data-ttu-id="4858a-179">伺服器共同作業應用程式的登錄項目</span><span class="sxs-lookup"><span data-stu-id="4858a-179">Registry Entries for a Server-based Collaboration Application</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4858a-180">名稱</span><span class="sxs-lookup"><span data-stu-id="4858a-180">Name</span></span></th>
<th><span data-ttu-id="4858a-181">Type</span><span class="sxs-lookup"><span data-stu-id="4858a-181">Type</span></span></th>
<th><span data-ttu-id="4858a-182">Data (資料)</span><span class="sxs-lookup"><span data-stu-id="4858a-182">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4858a-183">名稱</span><span class="sxs-lookup"><span data-stu-id="4858a-183">Name</span></span></p></td>
<td><p><span data-ttu-id="4858a-184">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="4858a-184">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="4858a-185">顯示在功能表上的應用程式名稱。</span><span class="sxs-lookup"><span data-stu-id="4858a-185">Name of the application as it appears on the menu.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4858a-186">ApplicationType</span><span class="sxs-lookup"><span data-stu-id="4858a-186">ApplicationType</span></span></p></td>
<td><p><span data-ttu-id="4858a-187">DWORD</span><span class="sxs-lookup"><span data-stu-id="4858a-187">DWORD</span></span></p></td>
<td><p><span data-ttu-id="4858a-188">值 = 1。</span><span class="sxs-lookup"><span data-stu-id="4858a-188">Value = 1.</span></span> <span data-ttu-id="4858a-189">將應用程式類型設定成通訊協定。</span><span class="sxs-lookup"><span data-stu-id="4858a-189">Sets the application type to protocol.</span></span> <span data-ttu-id="4858a-190">其他可能的值則在這個情況不適用。</span><span class="sxs-lookup"><span data-stu-id="4858a-190">The other possible values do not apply in this case.</span></span> <span data-ttu-id="4858a-191">如果不存在，ApplicationType 設為 0 （可執行檔）。</span><span class="sxs-lookup"><span data-stu-id="4858a-191">If not present, ApplicationType is set to 0 (executable).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4858a-192">路徑</span><span class="sxs-lookup"><span data-stu-id="4858a-192">Path</span></span></p></td>
<td><p><span data-ttu-id="4858a-193">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="4858a-193">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="4858a-194">用來啟動共同作業應用程式的通訊協定。</span><span class="sxs-lookup"><span data-stu-id="4858a-194">Protocol used to start the collaboration application.</span></span> <span data-ttu-id="4858a-195">Live Meeting 2007，路徑的值設為<code>meet:%conf-uri%</code>。</span><span class="sxs-lookup"><span data-stu-id="4858a-195">For Live Meeting 2007, the value of Path is set to <code>meet:%conf-uri%</code>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4858a-196">SessionType</span><span class="sxs-lookup"><span data-stu-id="4858a-196">SessionType</span></span></p></td>
<td><p><span data-ttu-id="4858a-197">DWORD</span><span class="sxs-lookup"><span data-stu-id="4858a-197">DWORD</span></span></p></td>
<td><p><span data-ttu-id="4858a-p114">0 = 本機工作階段。在本機電腦上啟動應用程式。</span><span class="sxs-lookup"><span data-stu-id="4858a-p114">0 = Local session. The application is started on the local computer.</span></span></p>
<p><span data-ttu-id="4858a-200">1 = 兩方工作階段 (預設)。</span><span class="sxs-lookup"><span data-stu-id="4858a-200">1 = Two-party session (default).</span></span> <span data-ttu-id="4858a-201">Lync 2013 啟動在本機上，在應用程式，然後將系統通知傳送給其他使用者。</span><span class="sxs-lookup"><span data-stu-id="4858a-201">Lync 2013 starts the application locally, and then sends a system notification to the other user.</span></span> <span data-ttu-id="4858a-202">另一位使用者按一下通知並在他們的電腦上啟動指定的應用程式。</span><span class="sxs-lookup"><span data-stu-id="4858a-202">The other user clicks the notification and starts the specified application on their computer.</span></span></p>
<p><span data-ttu-id="4858a-203">2 = 多方工作階段。</span><span class="sxs-lookup"><span data-stu-id="4858a-203">2 = Multiparty session.</span></span> <span data-ttu-id="4858a-204">Lync 2013 啟動在本機上，在應用程式，然後將系統通知傳送給其他使用者，提示使用者在其電腦上啟動指定的應用程式。</span><span class="sxs-lookup"><span data-stu-id="4858a-204">Lync 2013 starts the application locally, and then sends system notifications to the other users, prompting them to start the specified application on their computer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4858a-205">MCUType</span><span class="sxs-lookup"><span data-stu-id="4858a-205">MCUType</span></span></p></td>
<td><p><span data-ttu-id="4858a-206">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="4858a-206">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="4858a-207">DATA = 伺服器的類型。</span><span class="sxs-lookup"><span data-stu-id="4858a-207">DATA = The type of server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4858a-208">ExtensibleMenu</span><span class="sxs-lookup"><span data-stu-id="4858a-208">ExtensibleMenu</span></span></p></td>
<td><p><span data-ttu-id="4858a-209">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="4858a-209">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="4858a-210">此命令將會出現的位置，功能表清單以分號分隔。</span><span class="sxs-lookup"><span data-stu-id="4858a-210">A list of the menus where this command will appear, separated by semicolons.</span></span> <span data-ttu-id="4858a-211">可能的值有：</span><span class="sxs-lookup"><span data-stu-id="4858a-211">Possible values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="4858a-212">MainWindowActions</span><span class="sxs-lookup"><span data-stu-id="4858a-212">MainWindowActions</span></span></p></li>
<li><p><span data-ttu-id="4858a-213">MainWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="4858a-213">MainWindowRightClick</span></span></p></li>
<li><p><span data-ttu-id="4858a-214">ConversationWindowActions</span><span class="sxs-lookup"><span data-stu-id="4858a-214">ConversationWindowActions</span></span></p></li>
<li><p><span data-ttu-id="4858a-215">ConversationWindowButton</span><span class="sxs-lookup"><span data-stu-id="4858a-215">ConversationWindowButton</span></span></p></li>
<li><p><span data-ttu-id="4858a-216">ConversationWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="4858a-216">ConversationWindowRightClick</span></span></p></li>
</ul>
<p><span data-ttu-id="4858a-217">如果沒有定義 ExtensibleMenu ，會使用 MainWindowRightClick 和 ConversationWindowActions 的預設值。</span><span class="sxs-lookup"><span data-stu-id="4858a-217">If ExtensibleMenu is not defined, the default values of MainWindowRightClick and ConversationWindowActions are used.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4858a-218">下列範例會啟動 ADatum Collaboration Client 從 Lync 2013 內的命令：</span><span class="sxs-lookup"><span data-stu-id="4858a-218">The following example adds commands to start ADatum Collaboration Client from within Lync 2013:</span></span>

    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager]
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager\Apps]
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager\Apps\{27877e66-615c-4582-ab88-0cb2ca05d951}]
    "Path"="meet:%conf-uri%"
    "SessionType"=dword:00000002
    "LiveServerIntegration"=dword:00000001
    "ApplicationType"=dword:00000001
    "Name"="ADatum Collaboration Client"
    "MCUType"="Data"
    "Extensiblemenu"="MainWindowActions;MainWindowRightClick;ConversationWindowActions;ConversationWindowRightClick"

</div>

</div>

<span> </span>

</div>

</div>

</div>

