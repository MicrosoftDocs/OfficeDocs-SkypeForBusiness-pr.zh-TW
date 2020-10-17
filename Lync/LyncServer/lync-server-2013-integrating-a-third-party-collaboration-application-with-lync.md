---
title: 整合協力廠商共同作業應用程式與 Lync
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
ms.openlocfilehash: e7bbe3f6439b357253ae49a5c1609319b6a91bfb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534752"
---
# <a name="integrating-a-third-party-collaboration-application-with-lync-server-2013"></a><span data-ttu-id="20506-102">整合協力廠商共同作業應用程式與 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="20506-102">Integrating a third-party collaboration application with Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="20506-103">_**主題上次修改日期：** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="20506-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="20506-104">您可以透過將應用程式的相關資訊新增至登錄，以整合 Lync 2013 與任何協力廠商的線上共同作業應用程式。</span><span class="sxs-lookup"><span data-stu-id="20506-104">You can integrate Lync 2013 with any third-party online collaboration application by adding information about the application to the registry.</span></span> <span data-ttu-id="20506-105">您可以使用 Lync 2013 啟動在內部伺服器、網際網路服務或兩者兩者上裝載的資料會議會話。</span><span class="sxs-lookup"><span data-stu-id="20506-105">You can use Lync 2013 to start data conferencing sessions hosted on an in-house server, an Internet-based service, or both.</span></span> <span data-ttu-id="20506-106">您可以從 [連絡人清單] 或從現有的立即訊息、語音或視訊工作階段，啟動共同作業或資料會議工作階段。</span><span class="sxs-lookup"><span data-stu-id="20506-106">The collaboration or data conferencing session can be started from the Contacts list or from an existing instant messaging, voice, or video session.</span></span> <span data-ttu-id="20506-107">Lync 2013 的行為方式只是啟動應用程式的工具。</span><span class="sxs-lookup"><span data-stu-id="20506-107">Lync 2013 acts only as the vehicle for starting the application.</span></span> <span data-ttu-id="20506-108">在您開始線上共同作業會話後，任何現有的 Lync 2013 交談都會保持使用中狀態。</span><span class="sxs-lookup"><span data-stu-id="20506-108">Any existing Lync 2013 conversations remain active after the online collaboration session has begun.</span></span>

<span data-ttu-id="20506-109">下列各節說明如何使用網際網路型和伺服器型共同作業應用程式來整合 Lync 2013。</span><span class="sxs-lookup"><span data-stu-id="20506-109">The following sections describe how to integrate Lync 2013 with Internet-based and server-based collaboration applications.</span></span>

<div>

## <a name="integrating-an-internet-based-collaboration-application-with-lync-2013"></a><span data-ttu-id="20506-110">整合 Internet-Based 協同作業應用程式與 Lync 2013</span><span class="sxs-lookup"><span data-stu-id="20506-110">Integrating an Internet-Based Collaboration Application with Lync 2013</span></span>

<span data-ttu-id="20506-111">基本上，與協力廠商共同作業應用程式整合相關的步驟如下：</span><span class="sxs-lookup"><span data-stu-id="20506-111">Generally, the steps involved in integrating a third-party collaboration application are as follows:</span></span>

1.  <span data-ttu-id="20506-112">應用程式的相關資訊會新增到登錄中。</span><span class="sxs-lookup"><span data-stu-id="20506-112">Information about the application is added to the registry.</span></span>

2.  <span data-ttu-id="20506-113">召集人登入 Lync 2013，並選取連絡人以進行資料共用和共同作業。</span><span class="sxs-lookup"><span data-stu-id="20506-113">The organizer signs in to Lync 2013 and selects contacts for data sharing and collaboration.</span></span> <span data-ttu-id="20506-114">或者，召集人可能已經在交談中，並決定新增資料會議。</span><span class="sxs-lookup"><span data-stu-id="20506-114">Or, the organizer may already be in a conversation and decide to add data conferencing.</span></span>

3.  <span data-ttu-id="20506-115">Lync 2013 讀取登錄、啟動共同作業應用程式，然後將自訂的 SIP 郵件（appINVITE）傳送給選取的參與者。</span><span class="sxs-lookup"><span data-stu-id="20506-115">Lync 2013 reads the registry, starts the collaboration application, and then sends a custom SIP message—an appINVITE—to the selected participants.</span></span>

4.  <span data-ttu-id="20506-116">參與者會接受邀請，並在每個人的電腦上啟動共同作業應用程式。</span><span class="sxs-lookup"><span data-stu-id="20506-116">Participants accept the invitation, and the collaboration application is started on each person’s computer.</span></span> <span data-ttu-id="20506-117">Lync 2013 會使用登錄來判斷要使用的共同作業應用程式，然後使用 appINVITE 消息中包含的參數來啟動該應用程式。</span><span class="sxs-lookup"><span data-stu-id="20506-117">Lync 2013 uses the registry to determine which collaboration application to use, and then starts that application by using the parameters included in the appINVITE message.</span></span>

<span data-ttu-id="20506-118">下表說明整合以網際網路為基礎之共同作業應用程式與 Lync 2013 的必要登錄專案。</span><span class="sxs-lookup"><span data-stu-id="20506-118">The following table describes the registry entries required to integrate an Internet-based collaboration application with Lync 2013.</span></span> <span data-ttu-id="20506-119">這些專案會放在登錄中的下列位置：</span><span class="sxs-lookup"><span data-stu-id="20506-119">These entries are placed in the registry in the following location:</span></span>

  - <span data-ttu-id="20506-120">HKEY \_ LOCAL \_ MACHINE \\ 軟體 \\ Microsoft \\ Office \\ 15.0 \\ Lync \\ SessionManager \\ 應用程式 \\ 參數</span><span class="sxs-lookup"><span data-stu-id="20506-120">HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters</span></span>

### <a name="registry-entries-for-an-internet-based-collaboration-application"></a><span data-ttu-id="20506-121">網際網路共同作業應用程式的登錄項目</span><span class="sxs-lookup"><span data-stu-id="20506-121">Registry Entries for an Internet-based Collaboration Application</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="20506-122">名稱</span><span class="sxs-lookup"><span data-stu-id="20506-122">Name</span></span></th>
<th><span data-ttu-id="20506-123">類型</span><span class="sxs-lookup"><span data-stu-id="20506-123">Type</span></span></th>
<th><span data-ttu-id="20506-124">Data (資料)</span><span class="sxs-lookup"><span data-stu-id="20506-124">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="20506-125">姓名</span><span class="sxs-lookup"><span data-stu-id="20506-125">Name</span></span></p></td>
<td><p><span data-ttu-id="20506-126">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="20506-126">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="20506-127">Lync 2013 功能表的應用程式名稱。</span><span class="sxs-lookup"><span data-stu-id="20506-127">The application name for Lync 2013 menus.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20506-128">SmallIcon</span><span class="sxs-lookup"><span data-stu-id="20506-128">SmallIcon</span></span></p></td>
<td><p><span data-ttu-id="20506-129">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="20506-129">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="20506-130">16 像素 x 16 像素圖示 (BMP 或 PNG) 的路徑。</span><span class="sxs-lookup"><span data-stu-id="20506-130">Path to 16-pixel x 16-pixel icon, BMP or PNG.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="20506-131">路徑</span><span class="sxs-lookup"><span data-stu-id="20506-131">Path</span></span></p></td>
<td><p><span data-ttu-id="20506-132">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="20506-132">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="20506-133">啟動線上共同作業應用程式的參與者路徑。</span><span class="sxs-lookup"><span data-stu-id="20506-133">Participant path for starting the online collaboration application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20506-134">OriginatorPath</span><span class="sxs-lookup"><span data-stu-id="20506-134">OriginatorPath</span></span></p></td>
<td><p><span data-ttu-id="20506-135">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="20506-135">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="20506-136">啟動線上共同作業應用程式的召集人路徑。</span><span class="sxs-lookup"><span data-stu-id="20506-136">Organizer path for starting the online collaboration application.</span></span> <span data-ttu-id="20506-137">這個路徑可以包含一或多個自訂參數，做為 Parameters 子機碼中定義的參數。</span><span class="sxs-lookup"><span data-stu-id="20506-137">This path can contain one or more custom parameters as defined in the Parameters subkey.</span></span> <span data-ttu-id="20506-138">例如， <code>https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&amp;role=present&amp;pw=%param3%</code></span><span class="sxs-lookup"><span data-stu-id="20506-138">For example, <code>https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&amp;role=present&amp;pw=%param3%</code></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="20506-139">SessionType</span><span class="sxs-lookup"><span data-stu-id="20506-139">SessionType</span></span></p></td>
<td><p><span data-ttu-id="20506-140">DWORD</span><span class="sxs-lookup"><span data-stu-id="20506-140">DWORD</span></span></p></td>
<td><p><span data-ttu-id="20506-p106">0 = 本機工作階段。在本機電腦上啟動應用程式。</span><span class="sxs-lookup"><span data-stu-id="20506-p106">0 = Local session. The application is started on the local computer.</span></span></p>
<p><span data-ttu-id="20506-143">1 = 兩方工作階段 (預設)。</span><span class="sxs-lookup"><span data-stu-id="20506-143">1 = Two-party session (default).</span></span> <span data-ttu-id="20506-144">Lync 2013 會在本機啟動應用程式，然後將系統通知傳送給另一個使用者。</span><span class="sxs-lookup"><span data-stu-id="20506-144">Lync 2013 starts the application locally, and then sends a system notification to the other user.</span></span> <span data-ttu-id="20506-145">另一位使用者按一下通知並在他們的電腦上啟動指定的應用程式。</span><span class="sxs-lookup"><span data-stu-id="20506-145">The other user clicks the notification and starts the specified application on their computer.</span></span></p>
<p><span data-ttu-id="20506-146">2 = 多方工作階段。</span><span class="sxs-lookup"><span data-stu-id="20506-146">2 = Multiparty session.</span></span> <span data-ttu-id="20506-147">Lync 2013 會在本機啟動應用程式，然後將系統通知傳送給其他使用者，以提示使用者在自己的電腦上啟動指定的應用程式。</span><span class="sxs-lookup"><span data-stu-id="20506-147">Lync 2013 starts the application locally, and then sends system notifications to the other users, prompting them to start the specified application on their own computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20506-148">ExensibleMenu</span><span class="sxs-lookup"><span data-stu-id="20506-148">ExensibleMenu</span></span></p></td>
<td><p><span data-ttu-id="20506-149">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="20506-149">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="20506-p109">會出現這個命令的功能表清單 (以分號分隔)。可能的值有：</span><span class="sxs-lookup"><span data-stu-id="20506-p109">A list of the menus where this command will appear, separated by semi-colons. Possible values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="20506-152">MainWindowActions</span><span class="sxs-lookup"><span data-stu-id="20506-152">MainWindowActions</span></span></p></li>
<li><p><span data-ttu-id="20506-153">MainWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="20506-153">MainWindowRightClick</span></span></p></li>
<li><p><span data-ttu-id="20506-154">ConversationWindowActions</span><span class="sxs-lookup"><span data-stu-id="20506-154">ConversationWindowActions</span></span></p></li>
<li><p><span data-ttu-id="20506-155">ConversationWindowButton</span><span class="sxs-lookup"><span data-stu-id="20506-155">ConversationWindowButton</span></span></p></li>
<li><p><span data-ttu-id="20506-156">ConversationWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="20506-156">ConversationWindowRightClick</span></span></p></li>
</ul>
<p><span data-ttu-id="20506-157">如果沒有定義 ExtensibleMenu ，會使用 MainWindowRightClick 和 ConversationWindowActions 的預設值。</span><span class="sxs-lookup"><span data-stu-id="20506-157">If ExtensibleMenu is not defined, the default values of MainWindowRightClick and ConversationWindowActions are used.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="20506-158">下表說明參數的登錄項目。</span><span class="sxs-lookup"><span data-stu-id="20506-158">The following table describes the registry entries for parameters.</span></span> <span data-ttu-id="20506-159">這些專案位於 HKEY 目前的 \_ \_ 使用者 \\ 軟體 \\ Microsoft \\ Office \\ 15.0 \\ Lync \\ SessionManager \\ 應用程式 \\ 參數。</span><span class="sxs-lookup"><span data-stu-id="20506-159">These entries are place at HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters.</span></span>

### <a name="registry-entries-for-an-internet-based-collaboration-application"></a><span data-ttu-id="20506-160">網際網路共同作業應用程式的登錄項目</span><span class="sxs-lookup"><span data-stu-id="20506-160">Registry Entries for an Internet-based Collaboration Application</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="20506-161">名稱</span><span class="sxs-lookup"><span data-stu-id="20506-161">Name</span></span></th>
<th><span data-ttu-id="20506-162">類型</span><span class="sxs-lookup"><span data-stu-id="20506-162">Type</span></span></th>
<th><span data-ttu-id="20506-163">Data (資料)</span><span class="sxs-lookup"><span data-stu-id="20506-163">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="20506-164">Param1</span><span class="sxs-lookup"><span data-stu-id="20506-164">Param1</span></span></p></td>
<td><p><span data-ttu-id="20506-165">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="20506-165">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="20506-166">用於標記化格式 (<code>%Parm1%</code>) 將使用者特定值新增至 OriginatorPath 登錄機碼。</span><span class="sxs-lookup"><span data-stu-id="20506-166">Used in tokenized format (<code>%Parm1%</code>) to add user-specific values to the OriginatorPath registry key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20506-167">Param2</span><span class="sxs-lookup"><span data-stu-id="20506-167">Param2</span></span></p></td>
<td><p><span data-ttu-id="20506-168">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="20506-168">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="20506-169">請參閱 Param1。</span><span class="sxs-lookup"><span data-stu-id="20506-169">See Param1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="20506-170">Param3</span><span class="sxs-lookup"><span data-stu-id="20506-170">Param3</span></span></p></td>
<td><p><span data-ttu-id="20506-171">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="20506-171">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="20506-172">請參閱 Param1。</span><span class="sxs-lookup"><span data-stu-id="20506-172">See Param1.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="20506-173">下列範例登錄設定會整合 ADatum 協同作業用戶端與 Lync 2013：</span><span class="sxs-lookup"><span data-stu-id="20506-173">The following example registry settings integrate ADatum Collaboration Client with Lync 2013:</span></span>

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

## <a name="integrating-a-server-based-collaboration-application-with-lync-2013"></a><span data-ttu-id="20506-174">整合 Server-Based 協同作業應用程式與 Lync 2013</span><span class="sxs-lookup"><span data-stu-id="20506-174">Integrating a Server-Based Collaboration Application with Lync 2013</span></span>

<span data-ttu-id="20506-175">在 Lync 2013 中，新增用以啟動伺服器型共同作業應用程式的命令，與上一節中所述，將 Internet-Based 共同作業應用程式與 Lync 2013 整合在一起。</span><span class="sxs-lookup"><span data-stu-id="20506-175">The settings to add commands for starting a server-based collaboration application from within Lync 2013 are similar to those described in the previous section, Integrating an Internet-Based Collaboration Application with Lync 2013.</span></span> <span data-ttu-id="20506-176">不過，不需要 OriginatorPath，而且有些值已經變更。</span><span class="sxs-lookup"><span data-stu-id="20506-176">However, the OriginatorPath is not required, and some values are changed.</span></span> <span data-ttu-id="20506-177">登錄專案位於下列位置：</span><span class="sxs-lookup"><span data-stu-id="20506-177">Registry entries are placed in the following location:</span></span>

  - <span data-ttu-id="20506-178">HKEY \_ LOCAL \_ MACHINE \\ 軟體 \\ Microsoft \\ Office \\ 15.0 \\ Lync \\ SessionManager \\ 應用程式 \\ 參數</span><span class="sxs-lookup"><span data-stu-id="20506-178">HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters</span></span>

### <a name="registry-entries-for-a-server-based-collaboration-application"></a><span data-ttu-id="20506-179">伺服器共同作業應用程式的登錄項目</span><span class="sxs-lookup"><span data-stu-id="20506-179">Registry Entries for a Server-based Collaboration Application</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="20506-180">名稱</span><span class="sxs-lookup"><span data-stu-id="20506-180">Name</span></span></th>
<th><span data-ttu-id="20506-181">類型</span><span class="sxs-lookup"><span data-stu-id="20506-181">Type</span></span></th>
<th><span data-ttu-id="20506-182">Data (資料)</span><span class="sxs-lookup"><span data-stu-id="20506-182">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="20506-183">姓名</span><span class="sxs-lookup"><span data-stu-id="20506-183">Name</span></span></p></td>
<td><p><span data-ttu-id="20506-184">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="20506-184">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="20506-185">顯示在功能表上的應用程式名稱。</span><span class="sxs-lookup"><span data-stu-id="20506-185">Name of the application as it appears on the menu.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20506-186">ApplicationType</span><span class="sxs-lookup"><span data-stu-id="20506-186">ApplicationType</span></span></p></td>
<td><p><span data-ttu-id="20506-187">DWORD</span><span class="sxs-lookup"><span data-stu-id="20506-187">DWORD</span></span></p></td>
<td><p><span data-ttu-id="20506-188">值 = 1。</span><span class="sxs-lookup"><span data-stu-id="20506-188">Value = 1.</span></span> <span data-ttu-id="20506-189">將應用程式類型設定成通訊協定。</span><span class="sxs-lookup"><span data-stu-id="20506-189">Sets the application type to protocol.</span></span> <span data-ttu-id="20506-190">其他可能的值則在這個情況不適用。</span><span class="sxs-lookup"><span data-stu-id="20506-190">The other possible values do not apply in this case.</span></span> <span data-ttu-id="20506-191">如果不存在，ApplicationType 會設為 0 (可執行檔) 。</span><span class="sxs-lookup"><span data-stu-id="20506-191">If not present, ApplicationType is set to 0 (executable).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="20506-192">路徑</span><span class="sxs-lookup"><span data-stu-id="20506-192">Path</span></span></p></td>
<td><p><span data-ttu-id="20506-193">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="20506-193">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="20506-194">用來啟動共同作業應用程式的通訊協定。</span><span class="sxs-lookup"><span data-stu-id="20506-194">Protocol used to start the collaboration application.</span></span> <span data-ttu-id="20506-195">如果是 Live Meeting 2007，Path 的值會設為 <code>meet:%conf-uri%</code> 。</span><span class="sxs-lookup"><span data-stu-id="20506-195">For Live Meeting 2007, the value of Path is set to <code>meet:%conf-uri%</code>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20506-196">SessionType</span><span class="sxs-lookup"><span data-stu-id="20506-196">SessionType</span></span></p></td>
<td><p><span data-ttu-id="20506-197">DWORD</span><span class="sxs-lookup"><span data-stu-id="20506-197">DWORD</span></span></p></td>
<td><p><span data-ttu-id="20506-p114">0 = 本機工作階段。在本機電腦上啟動應用程式。</span><span class="sxs-lookup"><span data-stu-id="20506-p114">0 = Local session. The application is started on the local computer.</span></span></p>
<p><span data-ttu-id="20506-200">1 = 兩方工作階段 (預設)。</span><span class="sxs-lookup"><span data-stu-id="20506-200">1 = Two-party session (default).</span></span> <span data-ttu-id="20506-201">Lync 2013 會在本機啟動應用程式，然後將系統通知傳送給另一個使用者。</span><span class="sxs-lookup"><span data-stu-id="20506-201">Lync 2013 starts the application locally, and then sends a system notification to the other user.</span></span> <span data-ttu-id="20506-202">另一位使用者按一下通知並在他們的電腦上啟動指定的應用程式。</span><span class="sxs-lookup"><span data-stu-id="20506-202">The other user clicks the notification and starts the specified application on their computer.</span></span></p>
<p><span data-ttu-id="20506-203">2 = 多方工作階段。</span><span class="sxs-lookup"><span data-stu-id="20506-203">2 = Multiparty session.</span></span> <span data-ttu-id="20506-204">Lync 2013 會在本機啟動應用程式，然後將系統通知傳送給其他使用者，以提示使用者在其電腦上啟動指定的應用程式。</span><span class="sxs-lookup"><span data-stu-id="20506-204">Lync 2013 starts the application locally, and then sends system notifications to the other users, prompting them to start the specified application on their computer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="20506-205">MCUType</span><span class="sxs-lookup"><span data-stu-id="20506-205">MCUType</span></span></p></td>
<td><p><span data-ttu-id="20506-206">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="20506-206">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="20506-207">DATA = 伺服器的類型。</span><span class="sxs-lookup"><span data-stu-id="20506-207">DATA = The type of server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20506-208">ExtensibleMenu</span><span class="sxs-lookup"><span data-stu-id="20506-208">ExtensibleMenu</span></span></p></td>
<td><p><span data-ttu-id="20506-209">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="20506-209">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="20506-210">會出現這個命令的功能表清單，以分號分隔。</span><span class="sxs-lookup"><span data-stu-id="20506-210">A list of the menus where this command will appear, separated by semicolons.</span></span> <span data-ttu-id="20506-211">可能的值有：</span><span class="sxs-lookup"><span data-stu-id="20506-211">Possible values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="20506-212">MainWindowActions</span><span class="sxs-lookup"><span data-stu-id="20506-212">MainWindowActions</span></span></p></li>
<li><p><span data-ttu-id="20506-213">MainWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="20506-213">MainWindowRightClick</span></span></p></li>
<li><p><span data-ttu-id="20506-214">ConversationWindowActions</span><span class="sxs-lookup"><span data-stu-id="20506-214">ConversationWindowActions</span></span></p></li>
<li><p><span data-ttu-id="20506-215">ConversationWindowButton</span><span class="sxs-lookup"><span data-stu-id="20506-215">ConversationWindowButton</span></span></p></li>
<li><p><span data-ttu-id="20506-216">ConversationWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="20506-216">ConversationWindowRightClick</span></span></p></li>
</ul>
<p><span data-ttu-id="20506-217">如果沒有定義 ExtensibleMenu ，會使用 MainWindowRightClick 和 ConversationWindowActions 的預設值。</span><span class="sxs-lookup"><span data-stu-id="20506-217">If ExtensibleMenu is not defined, the default values of MainWindowRightClick and ConversationWindowActions are used.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="20506-218">下列範例會在 Lync 2013 中新增從 ADatum 協同作業用戶端開始的命令：</span><span class="sxs-lookup"><span data-stu-id="20506-218">The following example adds commands to start ADatum Collaboration Client from within Lync 2013:</span></span>

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

