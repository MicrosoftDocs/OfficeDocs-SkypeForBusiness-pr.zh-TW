---
title: Lync Server 2013：新增命令至 Lync 功能表
description: Lync Server 2013：新增命令至 Lync 功能表。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Adding commands to Lync menus
ms:assetid: a8443bc2-e234-4022-870a-00700f38b1ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412788(v=OCS.15)
ms:contentKeyID: 48185091
ms.date: 04/11/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ed4d62d085eaf115d107244ae50a7cc69e0aacd5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558229"
---
# <a name="adding-commands-to-lync-menus-in-lync-server-2013"></a><span data-ttu-id="29485-103">將命令新增至 Lync Server 2013 中的 Lync 功能表</span><span class="sxs-lookup"><span data-stu-id="29485-103">Adding commands to Lync menus in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="29485-104">_**主題上次修改日期：** 2016-04-11_</span><span class="sxs-lookup"><span data-stu-id="29485-104">_**Topic Last Modified:** 2016-04-11_</span></span>

<span data-ttu-id="29485-105">您可以將自訂命令新增至 Lync 2013 功能表，並將目前使用者及選取之連絡人的 SIP 統一資源識別項傳遞給該自訂命令啟動的應用程式 (URI) 。</span><span class="sxs-lookup"><span data-stu-id="29485-105">You can add custom commands to Lync 2013 menus and pass the SIP Uniform Resource Identifier (URI) of the current user and selected contacts to the application that the custom command starts.</span></span>

<span data-ttu-id="29485-106">您新增的自訂命令可以出現在下列一或多個功能表上：</span><span class="sxs-lookup"><span data-stu-id="29485-106">The custom commands that you add can appear on one or more of the following menus:</span></span>

  - <span data-ttu-id="29485-107">[工具] 功能表，在 Lync 主視窗中的功能表列上</span><span class="sxs-lookup"><span data-stu-id="29485-107">The Tools menu, on the menu bar in the Lync main window</span></span>

  - <span data-ttu-id="29485-108">連絡人清單中連絡人的快顯功能表</span><span class="sxs-lookup"><span data-stu-id="29485-108">The shortcut menu for contacts in the Contacts list</span></span>

  - <span data-ttu-id="29485-109">[更多選項] 功能表的 [交談] 視窗</span><span class="sxs-lookup"><span data-stu-id="29485-109">The More Options menu, in the Conversation window</span></span>

  - <span data-ttu-id="29485-110">在交談視窗參與者清單中列出之人員的快顯功能表</span><span class="sxs-lookup"><span data-stu-id="29485-110">The shortcut menu for people listed in the Conversation window participant list</span></span>

  - <span data-ttu-id="29485-111">連絡人卡片中的 [選項] 功能表</span><span class="sxs-lookup"><span data-stu-id="29485-111">The options menu in a contact card</span></span>

<span data-ttu-id="29485-112">您可以為兩種類型的應用程式定義自訂命令：執行下列其中一項的應用程式：</span><span class="sxs-lookup"><span data-stu-id="29485-112">You can define custom commands for two types of applications—applications that do either of the following:</span></span>

  - <span data-ttu-id="29485-113">僅適用于目前的使用者，並在本機電腦上啟動。</span><span class="sxs-lookup"><span data-stu-id="29485-113">Apply only to the current user and are started on the local computer.</span></span>

  - <span data-ttu-id="29485-114">包含其他使用者（例如線上共同作業計畫），且必須在每一位使用者的電腦上啟動。</span><span class="sxs-lookup"><span data-stu-id="29485-114">Involve additional users, such as an online collaboration program, and must be started on each user's computer.</span></span>

<span data-ttu-id="29485-115">您可以透過下列方式呼叫自訂命令：</span><span class="sxs-lookup"><span data-stu-id="29485-115">The custom command can be invoked in the following ways:</span></span>

  - <span data-ttu-id="29485-116">選取一或多個使用者，然後選擇自訂命令。</span><span class="sxs-lookup"><span data-stu-id="29485-116">Select one or more users, and then choose the custom command.</span></span>

  - <span data-ttu-id="29485-117">啟動兩方或多方交談，然後選擇自訂命令。</span><span class="sxs-lookup"><span data-stu-id="29485-117">Start a two-party or multiparty conversation, and then choose the custom command.</span></span>

<div>

## <a name="to-add-a-custom-command"></a><span data-ttu-id="29485-118">若要新增自訂命令</span><span class="sxs-lookup"><span data-stu-id="29485-118">To add a custom command</span></span>

<span data-ttu-id="29485-119">使用下表中的登錄設定，將命令新增至功能表。</span><span class="sxs-lookup"><span data-stu-id="29485-119">Use the registry settings in the following table to add a command to the menus.</span></span> <span data-ttu-id="29485-120">這些專案會放在登錄的下列其中一個位置：</span><span class="sxs-lookup"><span data-stu-id="29485-120">These entries are placed in the registry at one of the following locations:</span></span>

  - <span data-ttu-id="29485-121">針對32位作業系統： HKEY \_ LOCAL \_ MACHINE \\ 軟體 \\ Microsoft \\ Office \\ 15.0 \\ Lync \\ SessionManager \\ 應用程式</span><span class="sxs-lookup"><span data-stu-id="29485-121">For 32bit OS: HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps</span></span>

  - <span data-ttu-id="29485-122">針對64位作業系統： HKEY \_ LOCAL \_ MACHINE \\ 軟體 \\ Wow6432Node \\ Microsoft \\ Office \\ 15.0 \\ Lync \\ SessionManager \\ 應用程式</span><span class="sxs-lookup"><span data-stu-id="29485-122">For 64bit OS: HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps</span></span>

### <a name="custom-command-registry-entries"></a><span data-ttu-id="29485-123">自訂命令登錄專案</span><span class="sxs-lookup"><span data-stu-id="29485-123">Custom Command Registry Entries</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="29485-124">名稱</span><span class="sxs-lookup"><span data-stu-id="29485-124">Name</span></span></th>
<th><span data-ttu-id="29485-125">類型</span><span class="sxs-lookup"><span data-stu-id="29485-125">Type</span></span></th>
<th><span data-ttu-id="29485-126">Data (資料)</span><span class="sxs-lookup"><span data-stu-id="29485-126">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="29485-127">姓名</span><span class="sxs-lookup"><span data-stu-id="29485-127">Name</span></span></p></td>
<td><p><span data-ttu-id="29485-128">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="29485-128">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="29485-129">顯示在功能表上的應用程式名稱。</span><span class="sxs-lookup"><span data-stu-id="29485-129">Name of the application as it appears on the menu.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29485-130">ApplicationType</span><span class="sxs-lookup"><span data-stu-id="29485-130">ApplicationType</span></span></p></td>
<td><p><span data-ttu-id="29485-131">DWORD</span><span class="sxs-lookup"><span data-stu-id="29485-131">DWORD</span></span></p></td>
<td><p><span data-ttu-id="29485-132">0 = 可執行檔 (預設) </span><span class="sxs-lookup"><span data-stu-id="29485-132">0 = Executable (default)</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="29485-133">需要 ApplicationInstallPath。</span><span class="sxs-lookup"><span data-stu-id="29485-133">Requires ApplicationInstallPath.</span></span>


</div>
<p><span data-ttu-id="29485-134">1 = 通訊協定</span><span class="sxs-lookup"><span data-stu-id="29485-134">1 = Protocol</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29485-135">ApplicationInstallPath</span><span class="sxs-lookup"><span data-stu-id="29485-135">ApplicationInstallPath</span></span></p></td>
<td><p><span data-ttu-id="29485-136">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="29485-136">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="29485-137">可執行檔的完整路徑。</span><span class="sxs-lookup"><span data-stu-id="29485-137">Full path of the executable.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="29485-138">如果 ApplicationType 為 0 (可執行檔) 則必須指定。</span><span class="sxs-lookup"><span data-stu-id="29485-138">Must be specified if ApplicationType is 0 (Executable).</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29485-139">路徑</span><span class="sxs-lookup"><span data-stu-id="29485-139">Path</span></span></p></td>
<td><p><span data-ttu-id="29485-140">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="29485-140">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="29485-141">要與任何參數一起啟動的完整路徑，包括預設參數<em>% user 識別碼% user 識別碼</em>% <em>。</em></span><span class="sxs-lookup"><span data-stu-id="29485-141">Full path to be started along with any parameters, including the default parameters <em>%user-id%</em> and <em>%contact-id%</em>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29485-142">SessionType</span><span class="sxs-lookup"><span data-stu-id="29485-142">SessionType</span></span></p></td>
<td><p><span data-ttu-id="29485-143">DWORD</span><span class="sxs-lookup"><span data-stu-id="29485-143">DWORD</span></span></p></td>
<td><p><span data-ttu-id="29485-p102">0 = 本機工作階段。在本機電腦上啟動應用程式。</span><span class="sxs-lookup"><span data-stu-id="29485-p102">0 = Local session. The application is started on the local computer.</span></span></p>
<p><span data-ttu-id="29485-146">1 = 兩方工作階段 (預設)。</span><span class="sxs-lookup"><span data-stu-id="29485-146">1 = Two-party session (default).</span></span> <span data-ttu-id="29485-147">Lync 2013 會在本機啟動應用程式，然後將桌面通知傳送給另一個使用者。</span><span class="sxs-lookup"><span data-stu-id="29485-147">Lync 2013 starts the application locally and then sends a desktop notification to the other user.</span></span> <span data-ttu-id="29485-148">另一部使用者按一下通知，以在其電腦上啟動應用程式。</span><span class="sxs-lookup"><span data-stu-id="29485-148">The other user clicks the notification to start the application on their computer.</span></span></p>
<p><span data-ttu-id="29485-149">2 = 多方工作階段。</span><span class="sxs-lookup"><span data-stu-id="29485-149">2 = Multiparty session.</span></span> <span data-ttu-id="29485-150">Lync 2013 會在本機啟動應用程式，然後將桌面通知傳送給其他使用者。</span><span class="sxs-lookup"><span data-stu-id="29485-150">Lync 2013 starts the application locally and then sends desktop notifications to the other users.</span></span> <span data-ttu-id="29485-151">另一部使用者按一下通知，以在其電腦上啟動指定的應用程式。</span><span class="sxs-lookup"><span data-stu-id="29485-151">The other user clicks the notification to start the specified application on their computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29485-152">ExtensibleMenu</span><span class="sxs-lookup"><span data-stu-id="29485-152">ExtensibleMenu</span></span></p></td>
<td><p><span data-ttu-id="29485-153">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="29485-153">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="29485-154">會出現這個命令的功能表清單，以分號分隔。</span><span class="sxs-lookup"><span data-stu-id="29485-154">A list of the menus where this command will appear, separated by semicolons.</span></span> <span data-ttu-id="29485-155">可能的值有：</span><span class="sxs-lookup"><span data-stu-id="29485-155">Possible values are:</span></span></p>
<p><span data-ttu-id="29485-156">MainWindowActions</span><span class="sxs-lookup"><span data-stu-id="29485-156">MainWindowActions</span></span></p>
<p><span data-ttu-id="29485-157">MainWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="29485-157">MainWindowRightClick</span></span></p>
<p><span data-ttu-id="29485-158">ConversationWindowActions</span><span class="sxs-lookup"><span data-stu-id="29485-158">ConversationWindowActions</span></span></p>
<p><span data-ttu-id="29485-159">ConversationWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="29485-159">ConversationWindowRightClick</span></span></p>
<p><span data-ttu-id="29485-160">ContactCardMenu</span><span class="sxs-lookup"><span data-stu-id="29485-160">ContactCardMenu</span></span></p>
<p><span data-ttu-id="29485-161">如果沒有定義 ExtensibleMenu ，會使用 MainWindowRightClick 和 ConversationWindowActions 的預設值。</span><span class="sxs-lookup"><span data-stu-id="29485-161">If ExtensibleMenu is not defined, the default values of MainWindowRightClick and ConversationWindowActions are used.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="29485-162">例如，下列登錄編輯程式 (。REG) file 顯示在 [交談] 視窗中，將 Contoso Sales Contact Manager 功能表項目新增至 [動作] 功能表的結果：</span><span class="sxs-lookup"><span data-stu-id="29485-162">For example, the following Registry Editor (.REG) file shows the results of adding a Contoso Sales Contact Manager menu item to Actions menu in the Conversation window:</span></span>

    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Office\15.0\Lync\SessionManager\Apps\{1F9F07C6-7E0B-462B-AAD7-98C6DBEA8F69}]
    "Name"="Contoso Sales Contact Manager"
    "HelpMessage"="The Contoso Sales Contact Manager is not installed. Contact the Help Desk for more information."
    "ApplicationType"=dword:00000000
    "ApplicationInstallPath"="C:\\cscm.exe"
    "Path"="C:\\cscm.exe %user-id% %contact-id%"
    "SessionType"=dword:00000001
    "ExtensibleMenu"="ConversationWindowActions;MainWindowRightClick"

</div>

<div>

## <a name="to-access-a-custom-command"></a><span data-ttu-id="29485-163">存取自訂命令</span><span class="sxs-lookup"><span data-stu-id="29485-163">To access a custom command</span></span>

<span data-ttu-id="29485-164">若要在新增自訂命令之後存取它，請根據您定義的 ExtensibleMenu 值，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="29485-164">To access a custom command after it is added, do one of the following, depending on the ExtensibleMenu values that you define:</span></span>

  - <span data-ttu-id="29485-165">**MainWindowActions**    在 Lync 主視窗中，按一下 [**工具**]，然後按一下您的自訂命令。</span><span class="sxs-lookup"><span data-stu-id="29485-165">**MainWindowActions**   In the Lync main window, click **Tools**, and then click your custom command.</span></span>

  - <span data-ttu-id="29485-166">**MainWindowRightClick**    在 Lync 主視窗中，以滑鼠右鍵按一下連絡人，然後按一下您的自訂命令。</span><span class="sxs-lookup"><span data-stu-id="29485-166">**MainWindowRightClick**   In the Lync main window, right-click a contact, and then click your custom command.</span></span>

  - <span data-ttu-id="29485-167">**ConversationWindowActions**    在 [交談] 視窗中，按一下 [**其他選項**] 圖示，然後按一下您的自訂命令。</span><span class="sxs-lookup"><span data-stu-id="29485-167">**ConversationWindowActions**   In the Conversation window, click the **More Options** icon, and then click your custom command.</span></span>

  - <span data-ttu-id="29485-168">**ConversationWindowRightClick**    在 [交談] 視窗中，以滑鼠右鍵按一下連絡人名稱，然後按一下您的自訂命令。</span><span class="sxs-lookup"><span data-stu-id="29485-168">**ConversationWindowRightClick**   In the Conversation window, right-click a contact name, and then click your custom command.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

