---
title: Lync Server 2013： 將命令新增至 Lync 功能表
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
ms.openlocfilehash: 96a0df07a44392857f4384a1285245229874cdaa
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038605"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="adding-commands-to-lync-menus-in-lync-server-2013"></a><span data-ttu-id="0b957-102">將命令新增至 Lync Server 2013 中的 Lync 功能表</span><span class="sxs-lookup"><span data-stu-id="0b957-102">Adding commands to Lync menus in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0b957-103">_**主題上次修改日期：** 2016年-04-11_</span><span class="sxs-lookup"><span data-stu-id="0b957-103">_**Topic Last Modified:** 2016-04-11_</span></span>

<span data-ttu-id="0b957-104">您可以將自訂命令新增至 Lync 2013 功能表，並將 SIP 統一資源識別元 (URI) 的目前使用者] 和 [所選的連絡人傳遞至自訂命令啟動的應用程式。</span><span class="sxs-lookup"><span data-stu-id="0b957-104">You can add custom commands to Lync 2013 menus and pass the SIP Uniform Resource Identifier (URI) of the current user and selected contacts to the application that the custom command starts.</span></span>

<span data-ttu-id="0b957-105">您新增的自訂命令可以出現在一或多個下列功能表上：</span><span class="sxs-lookup"><span data-stu-id="0b957-105">The custom commands that you add can appear on one or more of the following menus:</span></span>

  - <span data-ttu-id="0b957-106">[工具] 功能表上的功能表列，在 Lync 主視窗</span><span class="sxs-lookup"><span data-stu-id="0b957-106">The Tools menu, on the menu bar in the Lync main window</span></span>

  - <span data-ttu-id="0b957-107">在 [連絡人] 清單中的連絡人快顯功能表</span><span class="sxs-lookup"><span data-stu-id="0b957-107">The shortcut menu for contacts in the Contacts list</span></span>

  - <span data-ttu-id="0b957-108">[更多選項] 功能表中 [交談] 視窗</span><span class="sxs-lookup"><span data-stu-id="0b957-108">The More Options menu, in the Conversation window</span></span>

  - <span data-ttu-id="0b957-109">在 [交談] 視窗參與者清單中所列人員快顯功能表</span><span class="sxs-lookup"><span data-stu-id="0b957-109">The shortcut menu for people listed in the Conversation window participant list</span></span>

  - <span data-ttu-id="0b957-110">[選項] 功能表中的連絡人卡片</span><span class="sxs-lookup"><span data-stu-id="0b957-110">The options menu in a contact card</span></span>

<span data-ttu-id="0b957-111">您可以定義自訂命令以兩種類型的應用程式-應用程式，執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="0b957-111">You can define custom commands for two types of applications—applications that do either of the following:</span></span>

  - <span data-ttu-id="0b957-112">僅適用於目前的使用者和本機電腦上啟動。</span><span class="sxs-lookup"><span data-stu-id="0b957-112">Apply only to the current user and are started on the local computer.</span></span>

  - <span data-ttu-id="0b957-113">包含其他使用者，例如線上共同作業的程式，且必須每位使用者的電腦上啟動。</span><span class="sxs-lookup"><span data-stu-id="0b957-113">Involve additional users, such as an online collaboration program, and must be started on each user's computer.</span></span>

<span data-ttu-id="0b957-114">可以透過下列方式叫用自訂命令：</span><span class="sxs-lookup"><span data-stu-id="0b957-114">The custom command can be invoked in the following ways:</span></span>

  - <span data-ttu-id="0b957-115">選取一或多個使用者，然後選擇 [自訂命令。</span><span class="sxs-lookup"><span data-stu-id="0b957-115">Select one or more users, and then choose the custom command.</span></span>

  - <span data-ttu-id="0b957-116">啟動雙方或多方交談，，，然後選擇自訂命令。</span><span class="sxs-lookup"><span data-stu-id="0b957-116">Start a two-party or multiparty conversation, and then choose the custom command.</span></span>

<div>

## <a name="to-add-a-custom-command"></a><span data-ttu-id="0b957-117">若要新增自訂命令</span><span class="sxs-lookup"><span data-stu-id="0b957-117">To add a custom command</span></span>

<span data-ttu-id="0b957-118">使用下表中的登錄設定，可將命令新增至功能表。</span><span class="sxs-lookup"><span data-stu-id="0b957-118">Use the registry settings in the following table to add a command to the menus.</span></span> <span data-ttu-id="0b957-119">這些項目會放置在登錄的下列位置：</span><span class="sxs-lookup"><span data-stu-id="0b957-119">These entries are placed in the registry at one of the following locations:</span></span>

  - <span data-ttu-id="0b957-120">針對 32 位元作業系統： HKEY\_本機\_機器\\軟體\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\應用程式</span><span class="sxs-lookup"><span data-stu-id="0b957-120">For 32bit OS: HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps</span></span>

  - <span data-ttu-id="0b957-121">針對 64 位元的作業系統： HKEY\_本機\_機器\\軟體\\Wow6432Node\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\應用程式</span><span class="sxs-lookup"><span data-stu-id="0b957-121">For 64bit OS: HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps</span></span>

### <a name="custom-command-registry-entries"></a><span data-ttu-id="0b957-122">自訂命令登錄項目</span><span class="sxs-lookup"><span data-stu-id="0b957-122">Custom Command Registry Entries</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0b957-123">名稱</span><span class="sxs-lookup"><span data-stu-id="0b957-123">Name</span></span></th>
<th><span data-ttu-id="0b957-124">Type</span><span class="sxs-lookup"><span data-stu-id="0b957-124">Type</span></span></th>
<th><span data-ttu-id="0b957-125">Data (資料)</span><span class="sxs-lookup"><span data-stu-id="0b957-125">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0b957-126">名稱</span><span class="sxs-lookup"><span data-stu-id="0b957-126">Name</span></span></p></td>
<td><p><span data-ttu-id="0b957-127">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="0b957-127">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="0b957-128">顯示在功能表上的應用程式名稱。</span><span class="sxs-lookup"><span data-stu-id="0b957-128">Name of the application as it appears on the menu.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b957-129">ApplicationType</span><span class="sxs-lookup"><span data-stu-id="0b957-129">ApplicationType</span></span></p></td>
<td><p><span data-ttu-id="0b957-130">DWORD</span><span class="sxs-lookup"><span data-stu-id="0b957-130">DWORD</span></span></p></td>
<td><p><span data-ttu-id="0b957-131">0 = 可執行檔 （預設值）</span><span class="sxs-lookup"><span data-stu-id="0b957-131">0 = Executable (default)</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="0b957-132">需要 ApplicationInstallPath。</span><span class="sxs-lookup"><span data-stu-id="0b957-132">Requires ApplicationInstallPath.</span></span>


</div>
<p><span data-ttu-id="0b957-133">1 = 通訊協定</span><span class="sxs-lookup"><span data-stu-id="0b957-133">1 = Protocol</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b957-134">ApplicationInstallPath</span><span class="sxs-lookup"><span data-stu-id="0b957-134">ApplicationInstallPath</span></span></p></td>
<td><p><span data-ttu-id="0b957-135">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="0b957-135">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="0b957-136">可執行檔的完整路徑。</span><span class="sxs-lookup"><span data-stu-id="0b957-136">Full path of the executable.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="0b957-137">必須指定是否 ApplicationType 為 0 （可執行檔）。</span><span class="sxs-lookup"><span data-stu-id="0b957-137">Must be specified if ApplicationType is 0 (Executable).</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b957-138">路徑</span><span class="sxs-lookup"><span data-stu-id="0b957-138">Path</span></span></p></td>
<td><p><span data-ttu-id="0b957-139">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="0b957-139">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="0b957-140">為與任何參數，包括預設參數<em>%使用者識別碼 %</em>和<em>%連絡人識別碼 %</em>一起啟動的完整路徑。</span><span class="sxs-lookup"><span data-stu-id="0b957-140">Full path to be started along with any parameters, including the default parameters <em>%user-id%</em> and <em>%contact-id%</em>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b957-141">SessionType</span><span class="sxs-lookup"><span data-stu-id="0b957-141">SessionType</span></span></p></td>
<td><p><span data-ttu-id="0b957-142">DWORD</span><span class="sxs-lookup"><span data-stu-id="0b957-142">DWORD</span></span></p></td>
<td><p><span data-ttu-id="0b957-p102">0 = 本機工作階段。在本機電腦上啟動應用程式。</span><span class="sxs-lookup"><span data-stu-id="0b957-p102">0 = Local session. The application is started on the local computer.</span></span></p>
<p><span data-ttu-id="0b957-145">1 = 兩方工作階段 (預設)。</span><span class="sxs-lookup"><span data-stu-id="0b957-145">1 = Two-party session (default).</span></span> <span data-ttu-id="0b957-146">Lync 2013 啟動本機的應用程式，並再將桌面通知傳送給其他使用者。</span><span class="sxs-lookup"><span data-stu-id="0b957-146">Lync 2013 starts the application locally and then sends a desktop notification to the other user.</span></span> <span data-ttu-id="0b957-147">其他使用者點選其電腦上啟動應用程式的通知。</span><span class="sxs-lookup"><span data-stu-id="0b957-147">The other user clicks the notification to start the application on their computer.</span></span></p>
<p><span data-ttu-id="0b957-148">2 = 多方工作階段。</span><span class="sxs-lookup"><span data-stu-id="0b957-148">2 = Multiparty session.</span></span> <span data-ttu-id="0b957-149">Lync 2013 啟動本機的應用程式，並再將桌面通知傳送給其他使用者。</span><span class="sxs-lookup"><span data-stu-id="0b957-149">Lync 2013 starts the application locally and then sends desktop notifications to the other users.</span></span> <span data-ttu-id="0b957-150">其他使用者按一下通知給他們的電腦上啟動指定的應用程式。</span><span class="sxs-lookup"><span data-stu-id="0b957-150">The other user clicks the notification to start the specified application on their computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b957-151">ExtensibleMenu</span><span class="sxs-lookup"><span data-stu-id="0b957-151">ExtensibleMenu</span></span></p></td>
<td><p><span data-ttu-id="0b957-152">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="0b957-152">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="0b957-153">此命令將會出現的位置，功能表清單以分號分隔。</span><span class="sxs-lookup"><span data-stu-id="0b957-153">A list of the menus where this command will appear, separated by semicolons.</span></span> <span data-ttu-id="0b957-154">可能的值有：</span><span class="sxs-lookup"><span data-stu-id="0b957-154">Possible values are:</span></span></p>
<p><span data-ttu-id="0b957-155">MainWindowActions</span><span class="sxs-lookup"><span data-stu-id="0b957-155">MainWindowActions</span></span></p>
<p><span data-ttu-id="0b957-156">MainWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="0b957-156">MainWindowRightClick</span></span></p>
<p><span data-ttu-id="0b957-157">ConversationWindowActions</span><span class="sxs-lookup"><span data-stu-id="0b957-157">ConversationWindowActions</span></span></p>
<p><span data-ttu-id="0b957-158">ConversationWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="0b957-158">ConversationWindowRightClick</span></span></p>
<p><span data-ttu-id="0b957-159">ContactCardMenu</span><span class="sxs-lookup"><span data-stu-id="0b957-159">ContactCardMenu</span></span></p>
<p><span data-ttu-id="0b957-160">如果沒有定義 ExtensibleMenu ，會使用 MainWindowRightClick 和 ConversationWindowActions 的預設值。</span><span class="sxs-lookup"><span data-stu-id="0b957-160">If ExtensibleMenu is not defined, the default values of MainWindowRightClick and ConversationWindowActions are used.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="0b957-161">例如，下列登錄編輯程式 (。登錄） 檔案會顯示將 Contoso Sales Contact Manager 功能表項目新增至 [交談] 視窗中的 [動作] 功能表的結果：</span><span class="sxs-lookup"><span data-stu-id="0b957-161">For example, the following Registry Editor (.REG) file shows the results of adding a Contoso Sales Contact Manager menu item to Actions menu in the Conversation window:</span></span>

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

## <a name="to-access-a-custom-command"></a><span data-ttu-id="0b957-162">若要存取自訂命令</span><span class="sxs-lookup"><span data-stu-id="0b957-162">To access a custom command</span></span>

<span data-ttu-id="0b957-163">若要存取自訂命令後就當簡報加入，執行下列命令，根據您定義的 ExtensibleMenu 值其中一項：</span><span class="sxs-lookup"><span data-stu-id="0b957-163">To access a custom command after it is added, do one of the following, depending on the ExtensibleMenu values that you define:</span></span>

  - <span data-ttu-id="0b957-164">**MainWindowActions**   在 Lync 主視窗中，按一下 [**工具**]，然後按一下 [您的自訂命令。</span><span class="sxs-lookup"><span data-stu-id="0b957-164">**MainWindowActions**   In the Lync main window, click **Tools**, and then click your custom command.</span></span>

  - <span data-ttu-id="0b957-165">**MainWindowRightClick**   在 Lync 主視窗中，以滑鼠右鍵按一下連絡人，，，然後按一下 [您的自訂命令。</span><span class="sxs-lookup"><span data-stu-id="0b957-165">**MainWindowRightClick**   In the Lync main window, right-click a contact, and then click your custom command.</span></span>

  - <span data-ttu-id="0b957-166">**ConversationWindowActions**   中 [交談] 視窗中，按一下 [**更多選項**] 圖示，然後按一下 [您的自訂命令。</span><span class="sxs-lookup"><span data-stu-id="0b957-166">**ConversationWindowActions**   In the Conversation window, click the **More Options** icon, and then click your custom command.</span></span>

  - <span data-ttu-id="0b957-167">**ConversationWindowRightClick**   在 [交談] 視窗中，以滑鼠右鍵按一下連絡人名稱，，，然後按一下 [您的自訂命令。</span><span class="sxs-lookup"><span data-stu-id="0b957-167">**ConversationWindowRightClick**   In the Conversation window, right-click a contact name, and then click your custom command.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

