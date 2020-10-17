---
title: Lync Server 2013：新增命令至 Lync 功能表
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
ms.openlocfilehash: 738f745d4f91458b95e95e5cc5770c34ed4e8c88
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521350"
---
# <a name="adding-commands-to-lync-menus-in-lync-server-2013"></a><span data-ttu-id="878dd-102">將命令新增至 Lync Server 2013 中的 Lync 功能表</span><span class="sxs-lookup"><span data-stu-id="878dd-102">Adding commands to Lync menus in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="878dd-103">_**主題上次修改日期：** 2016-04-11_</span><span class="sxs-lookup"><span data-stu-id="878dd-103">_**Topic Last Modified:** 2016-04-11_</span></span>

<span data-ttu-id="878dd-104">您可以將自訂命令新增至 Lync 2013 功能表，並將目前使用者及選取之連絡人的 SIP 統一資源識別項傳遞給該自訂命令啟動的應用程式 (URI) 。</span><span class="sxs-lookup"><span data-stu-id="878dd-104">You can add custom commands to Lync 2013 menus and pass the SIP Uniform Resource Identifier (URI) of the current user and selected contacts to the application that the custom command starts.</span></span>

<span data-ttu-id="878dd-105">您新增的自訂命令可以出現在下列一或多個功能表上：</span><span class="sxs-lookup"><span data-stu-id="878dd-105">The custom commands that you add can appear on one or more of the following menus:</span></span>

  - <span data-ttu-id="878dd-106">[工具] 功能表，在 Lync 主視窗中的功能表列上</span><span class="sxs-lookup"><span data-stu-id="878dd-106">The Tools menu, on the menu bar in the Lync main window</span></span>

  - <span data-ttu-id="878dd-107">連絡人清單中連絡人的快顯功能表</span><span class="sxs-lookup"><span data-stu-id="878dd-107">The shortcut menu for contacts in the Contacts list</span></span>

  - <span data-ttu-id="878dd-108">[更多選項] 功能表的 [交談] 視窗</span><span class="sxs-lookup"><span data-stu-id="878dd-108">The More Options menu, in the Conversation window</span></span>

  - <span data-ttu-id="878dd-109">在交談視窗參與者清單中列出之人員的快顯功能表</span><span class="sxs-lookup"><span data-stu-id="878dd-109">The shortcut menu for people listed in the Conversation window participant list</span></span>

  - <span data-ttu-id="878dd-110">連絡人卡片中的 [選項] 功能表</span><span class="sxs-lookup"><span data-stu-id="878dd-110">The options menu in a contact card</span></span>

<span data-ttu-id="878dd-111">您可以為兩種類型的應用程式定義自訂命令：執行下列其中一項的應用程式：</span><span class="sxs-lookup"><span data-stu-id="878dd-111">You can define custom commands for two types of applications—applications that do either of the following:</span></span>

  - <span data-ttu-id="878dd-112">僅適用于目前的使用者，並在本機電腦上啟動。</span><span class="sxs-lookup"><span data-stu-id="878dd-112">Apply only to the current user and are started on the local computer.</span></span>

  - <span data-ttu-id="878dd-113">包含其他使用者（例如線上共同作業計畫），且必須在每一位使用者的電腦上啟動。</span><span class="sxs-lookup"><span data-stu-id="878dd-113">Involve additional users, such as an online collaboration program, and must be started on each user's computer.</span></span>

<span data-ttu-id="878dd-114">您可以透過下列方式呼叫自訂命令：</span><span class="sxs-lookup"><span data-stu-id="878dd-114">The custom command can be invoked in the following ways:</span></span>

  - <span data-ttu-id="878dd-115">選取一或多個使用者，然後選擇自訂命令。</span><span class="sxs-lookup"><span data-stu-id="878dd-115">Select one or more users, and then choose the custom command.</span></span>

  - <span data-ttu-id="878dd-116">啟動兩方或多方交談，然後選擇自訂命令。</span><span class="sxs-lookup"><span data-stu-id="878dd-116">Start a two-party or multiparty conversation, and then choose the custom command.</span></span>

<div>

## <a name="to-add-a-custom-command"></a><span data-ttu-id="878dd-117">若要新增自訂命令</span><span class="sxs-lookup"><span data-stu-id="878dd-117">To add a custom command</span></span>

<span data-ttu-id="878dd-118">使用下表中的登錄設定，將命令新增至功能表。</span><span class="sxs-lookup"><span data-stu-id="878dd-118">Use the registry settings in the following table to add a command to the menus.</span></span> <span data-ttu-id="878dd-119">這些專案會放在登錄的下列其中一個位置：</span><span class="sxs-lookup"><span data-stu-id="878dd-119">These entries are placed in the registry at one of the following locations:</span></span>

  - <span data-ttu-id="878dd-120">針對32位作業系統： HKEY \_ LOCAL \_ MACHINE \\ 軟體 \\ Microsoft \\ Office \\ 15.0 \\ Lync \\ SessionManager \\ 應用程式</span><span class="sxs-lookup"><span data-stu-id="878dd-120">For 32bit OS: HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps</span></span>

  - <span data-ttu-id="878dd-121">針對64位作業系統： HKEY \_ LOCAL \_ MACHINE \\ 軟體 \\ Wow6432Node \\ Microsoft \\ Office \\ 15.0 \\ Lync \\ SessionManager \\ 應用程式</span><span class="sxs-lookup"><span data-stu-id="878dd-121">For 64bit OS: HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps</span></span>

### <a name="custom-command-registry-entries"></a><span data-ttu-id="878dd-122">自訂命令登錄專案</span><span class="sxs-lookup"><span data-stu-id="878dd-122">Custom Command Registry Entries</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="878dd-123">名稱</span><span class="sxs-lookup"><span data-stu-id="878dd-123">Name</span></span></th>
<th><span data-ttu-id="878dd-124">類型</span><span class="sxs-lookup"><span data-stu-id="878dd-124">Type</span></span></th>
<th><span data-ttu-id="878dd-125">Data (資料)</span><span class="sxs-lookup"><span data-stu-id="878dd-125">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="878dd-126">姓名</span><span class="sxs-lookup"><span data-stu-id="878dd-126">Name</span></span></p></td>
<td><p><span data-ttu-id="878dd-127">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="878dd-127">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="878dd-128">顯示在功能表上的應用程式名稱。</span><span class="sxs-lookup"><span data-stu-id="878dd-128">Name of the application as it appears on the menu.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="878dd-129">ApplicationType</span><span class="sxs-lookup"><span data-stu-id="878dd-129">ApplicationType</span></span></p></td>
<td><p><span data-ttu-id="878dd-130">DWORD</span><span class="sxs-lookup"><span data-stu-id="878dd-130">DWORD</span></span></p></td>
<td><p><span data-ttu-id="878dd-131">0 = 可執行檔 (預設) </span><span class="sxs-lookup"><span data-stu-id="878dd-131">0 = Executable (default)</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="878dd-132">需要 ApplicationInstallPath。</span><span class="sxs-lookup"><span data-stu-id="878dd-132">Requires ApplicationInstallPath.</span></span>


</div>
<p><span data-ttu-id="878dd-133">1 = 通訊協定</span><span class="sxs-lookup"><span data-stu-id="878dd-133">1 = Protocol</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="878dd-134">ApplicationInstallPath</span><span class="sxs-lookup"><span data-stu-id="878dd-134">ApplicationInstallPath</span></span></p></td>
<td><p><span data-ttu-id="878dd-135">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="878dd-135">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="878dd-136">可執行檔的完整路徑。</span><span class="sxs-lookup"><span data-stu-id="878dd-136">Full path of the executable.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="878dd-137">如果 ApplicationType 為 0 (可執行檔) 則必須指定。</span><span class="sxs-lookup"><span data-stu-id="878dd-137">Must be specified if ApplicationType is 0 (Executable).</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="878dd-138">路徑</span><span class="sxs-lookup"><span data-stu-id="878dd-138">Path</span></span></p></td>
<td><p><span data-ttu-id="878dd-139">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="878dd-139">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="878dd-140">要與任何參數一起啟動的完整路徑，包括預設參數<em>% user 識別碼% user 識別碼</em>% <em>。</em></span><span class="sxs-lookup"><span data-stu-id="878dd-140">Full path to be started along with any parameters, including the default parameters <em>%user-id%</em> and <em>%contact-id%</em>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="878dd-141">SessionType</span><span class="sxs-lookup"><span data-stu-id="878dd-141">SessionType</span></span></p></td>
<td><p><span data-ttu-id="878dd-142">DWORD</span><span class="sxs-lookup"><span data-stu-id="878dd-142">DWORD</span></span></p></td>
<td><p><span data-ttu-id="878dd-p102">0 = 本機工作階段。在本機電腦上啟動應用程式。</span><span class="sxs-lookup"><span data-stu-id="878dd-p102">0 = Local session. The application is started on the local computer.</span></span></p>
<p><span data-ttu-id="878dd-145">1 = 兩方工作階段 (預設)。</span><span class="sxs-lookup"><span data-stu-id="878dd-145">1 = Two-party session (default).</span></span> <span data-ttu-id="878dd-146">Lync 2013 會在本機啟動應用程式，然後將桌面通知傳送給另一個使用者。</span><span class="sxs-lookup"><span data-stu-id="878dd-146">Lync 2013 starts the application locally and then sends a desktop notification to the other user.</span></span> <span data-ttu-id="878dd-147">另一部使用者按一下通知，以在其電腦上啟動應用程式。</span><span class="sxs-lookup"><span data-stu-id="878dd-147">The other user clicks the notification to start the application on their computer.</span></span></p>
<p><span data-ttu-id="878dd-148">2 = 多方工作階段。</span><span class="sxs-lookup"><span data-stu-id="878dd-148">2 = Multiparty session.</span></span> <span data-ttu-id="878dd-149">Lync 2013 會在本機啟動應用程式，然後將桌面通知傳送給其他使用者。</span><span class="sxs-lookup"><span data-stu-id="878dd-149">Lync 2013 starts the application locally and then sends desktop notifications to the other users.</span></span> <span data-ttu-id="878dd-150">另一部使用者按一下通知，以在其電腦上啟動指定的應用程式。</span><span class="sxs-lookup"><span data-stu-id="878dd-150">The other user clicks the notification to start the specified application on their computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="878dd-151">ExtensibleMenu</span><span class="sxs-lookup"><span data-stu-id="878dd-151">ExtensibleMenu</span></span></p></td>
<td><p><span data-ttu-id="878dd-152">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="878dd-152">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="878dd-153">會出現這個命令的功能表清單，以分號分隔。</span><span class="sxs-lookup"><span data-stu-id="878dd-153">A list of the menus where this command will appear, separated by semicolons.</span></span> <span data-ttu-id="878dd-154">可能的值有：</span><span class="sxs-lookup"><span data-stu-id="878dd-154">Possible values are:</span></span></p>
<p><span data-ttu-id="878dd-155">MainWindowActions</span><span class="sxs-lookup"><span data-stu-id="878dd-155">MainWindowActions</span></span></p>
<p><span data-ttu-id="878dd-156">MainWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="878dd-156">MainWindowRightClick</span></span></p>
<p><span data-ttu-id="878dd-157">ConversationWindowActions</span><span class="sxs-lookup"><span data-stu-id="878dd-157">ConversationWindowActions</span></span></p>
<p><span data-ttu-id="878dd-158">ConversationWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="878dd-158">ConversationWindowRightClick</span></span></p>
<p><span data-ttu-id="878dd-159">ContactCardMenu</span><span class="sxs-lookup"><span data-stu-id="878dd-159">ContactCardMenu</span></span></p>
<p><span data-ttu-id="878dd-160">如果沒有定義 ExtensibleMenu ，會使用 MainWindowRightClick 和 ConversationWindowActions 的預設值。</span><span class="sxs-lookup"><span data-stu-id="878dd-160">If ExtensibleMenu is not defined, the default values of MainWindowRightClick and ConversationWindowActions are used.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="878dd-161">例如，下列登錄編輯程式 (。REG) file 顯示在 [交談] 視窗中，將 Contoso Sales Contact Manager 功能表項目新增至 [動作] 功能表的結果：</span><span class="sxs-lookup"><span data-stu-id="878dd-161">For example, the following Registry Editor (.REG) file shows the results of adding a Contoso Sales Contact Manager menu item to Actions menu in the Conversation window:</span></span>

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

## <a name="to-access-a-custom-command"></a><span data-ttu-id="878dd-162">存取自訂命令</span><span class="sxs-lookup"><span data-stu-id="878dd-162">To access a custom command</span></span>

<span data-ttu-id="878dd-163">若要在新增自訂命令之後存取它，請根據您定義的 ExtensibleMenu 值，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="878dd-163">To access a custom command after it is added, do one of the following, depending on the ExtensibleMenu values that you define:</span></span>

  - <span data-ttu-id="878dd-164">**MainWindowActions**    在 Lync 主視窗中，按一下 [**工具**]，然後按一下您的自訂命令。</span><span class="sxs-lookup"><span data-stu-id="878dd-164">**MainWindowActions**   In the Lync main window, click **Tools**, and then click your custom command.</span></span>

  - <span data-ttu-id="878dd-165">**MainWindowRightClick**    在 Lync 主視窗中，以滑鼠右鍵按一下連絡人，然後按一下您的自訂命令。</span><span class="sxs-lookup"><span data-stu-id="878dd-165">**MainWindowRightClick**   In the Lync main window, right-click a contact, and then click your custom command.</span></span>

  - <span data-ttu-id="878dd-166">**ConversationWindowActions**    在 [交談] 視窗中，按一下 [**其他選項**] 圖示，然後按一下您的自訂命令。</span><span class="sxs-lookup"><span data-stu-id="878dd-166">**ConversationWindowActions**   In the Conversation window, click the **More Options** icon, and then click your custom command.</span></span>

  - <span data-ttu-id="878dd-167">**ConversationWindowRightClick**    在 [交談] 視窗中，以滑鼠右鍵按一下連絡人名稱，然後按一下您的自訂命令。</span><span class="sxs-lookup"><span data-stu-id="878dd-167">**ConversationWindowRightClick**   In the Conversation window, right-click a contact name, and then click your custom command.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

