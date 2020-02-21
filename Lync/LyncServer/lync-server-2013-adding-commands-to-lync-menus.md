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
ms.openlocfilehash: 5b6377824a7d96e6bb7b0ae6c60c79f3ee4c05b2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42203329"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="adding-commands-to-lync-menus-in-lync-server-2013"></a><span data-ttu-id="cecff-102">將命令新增至 Lync Server 2013 中的 Lync 功能表</span><span class="sxs-lookup"><span data-stu-id="cecff-102">Adding commands to Lync menus in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cecff-103">_**主題上次修改日期：** 2016年-04-11_</span><span class="sxs-lookup"><span data-stu-id="cecff-103">_**Topic Last Modified:** 2016-04-11_</span></span>

<span data-ttu-id="cecff-104">您可以將自訂命令新增至 Lync 2013 功能表，並將 SIP 統一資源識別元 (URI) 的目前使用者] 和 [所選的連絡人傳遞至自訂命令啟動的應用程式。</span><span class="sxs-lookup"><span data-stu-id="cecff-104">You can add custom commands to Lync 2013 menus and pass the SIP Uniform Resource Identifier (URI) of the current user and selected contacts to the application that the custom command starts.</span></span>

<span data-ttu-id="cecff-105">您新增的自訂命令可以出現在一或多個下列功能表上：</span><span class="sxs-lookup"><span data-stu-id="cecff-105">The custom commands that you add can appear on one or more of the following menus:</span></span>

  - <span data-ttu-id="cecff-106">[工具] 功能表上的功能表列，在 Lync 主視窗</span><span class="sxs-lookup"><span data-stu-id="cecff-106">The Tools menu, on the menu bar in the Lync main window</span></span>

  - <span data-ttu-id="cecff-107">在 [連絡人] 清單中的連絡人快顯功能表</span><span class="sxs-lookup"><span data-stu-id="cecff-107">The shortcut menu for contacts in the Contacts list</span></span>

  - <span data-ttu-id="cecff-108">[更多選項] 功能表中 [交談] 視窗</span><span class="sxs-lookup"><span data-stu-id="cecff-108">The More Options menu, in the Conversation window</span></span>

  - <span data-ttu-id="cecff-109">在 [交談] 視窗參與者清單中所列人員快顯功能表</span><span class="sxs-lookup"><span data-stu-id="cecff-109">The shortcut menu for people listed in the Conversation window participant list</span></span>

  - <span data-ttu-id="cecff-110">[選項] 功能表中的連絡人卡片</span><span class="sxs-lookup"><span data-stu-id="cecff-110">The options menu in a contact card</span></span>

<span data-ttu-id="cecff-111">您可以定義自訂命令以兩種類型的應用程式-應用程式，執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="cecff-111">You can define custom commands for two types of applications—applications that do either of the following:</span></span>

  - <span data-ttu-id="cecff-112">僅適用於目前的使用者和本機電腦上啟動。</span><span class="sxs-lookup"><span data-stu-id="cecff-112">Apply only to the current user and are started on the local computer.</span></span>

  - <span data-ttu-id="cecff-113">包含其他使用者，例如線上共同作業的程式，且必須每位使用者的電腦上啟動。</span><span class="sxs-lookup"><span data-stu-id="cecff-113">Involve additional users, such as an online collaboration program, and must be started on each user's computer.</span></span>

<span data-ttu-id="cecff-114">可以透過下列方式叫用自訂命令：</span><span class="sxs-lookup"><span data-stu-id="cecff-114">The custom command can be invoked in the following ways:</span></span>

  - <span data-ttu-id="cecff-115">選取一或多個使用者，然後選擇 [自訂命令。</span><span class="sxs-lookup"><span data-stu-id="cecff-115">Select one or more users, and then choose the custom command.</span></span>

  - <span data-ttu-id="cecff-116">啟動雙方或多方交談，，，然後選擇自訂命令。</span><span class="sxs-lookup"><span data-stu-id="cecff-116">Start a two-party or multiparty conversation, and then choose the custom command.</span></span>

<div>

## <a name="to-add-a-custom-command"></a><span data-ttu-id="cecff-117">若要新增自訂命令</span><span class="sxs-lookup"><span data-stu-id="cecff-117">To add a custom command</span></span>

<span data-ttu-id="cecff-118">使用下表中的登錄設定，可將命令新增至功能表。</span><span class="sxs-lookup"><span data-stu-id="cecff-118">Use the registry settings in the following table to add a command to the menus.</span></span> <span data-ttu-id="cecff-119">這些項目會放置在登錄的下列位置：</span><span class="sxs-lookup"><span data-stu-id="cecff-119">These entries are placed in the registry at one of the following locations:</span></span>

  - <span data-ttu-id="cecff-120">針對 32 位元作業系統： HKEY\_本機\_機器\\軟體\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\應用程式</span><span class="sxs-lookup"><span data-stu-id="cecff-120">For 32bit OS: HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps</span></span>

  - <span data-ttu-id="cecff-121">針對 64 位元的作業系統： HKEY\_本機\_機器\\軟體\\Wow6432Node\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\應用程式</span><span class="sxs-lookup"><span data-stu-id="cecff-121">For 64bit OS: HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps</span></span>

### <a name="custom-command-registry-entries"></a><span data-ttu-id="cecff-122">自訂命令登錄項目</span><span class="sxs-lookup"><span data-stu-id="cecff-122">Custom Command Registry Entries</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cecff-123">名稱</span><span class="sxs-lookup"><span data-stu-id="cecff-123">Name</span></span></th>
<th><span data-ttu-id="cecff-124">Type</span><span class="sxs-lookup"><span data-stu-id="cecff-124">Type</span></span></th>
<th><span data-ttu-id="cecff-125">Data (資料)</span><span class="sxs-lookup"><span data-stu-id="cecff-125">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cecff-126">名稱</span><span class="sxs-lookup"><span data-stu-id="cecff-126">Name</span></span></p></td>
<td><p><span data-ttu-id="cecff-127">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="cecff-127">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="cecff-128">顯示在功能表上的應用程式名稱。</span><span class="sxs-lookup"><span data-stu-id="cecff-128">Name of the application as it appears on the menu.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cecff-129">ApplicationType</span><span class="sxs-lookup"><span data-stu-id="cecff-129">ApplicationType</span></span></p></td>
<td><p><span data-ttu-id="cecff-130">DWORD</span><span class="sxs-lookup"><span data-stu-id="cecff-130">DWORD</span></span></p></td>
<td><p><span data-ttu-id="cecff-131">0 = 可執行檔 （預設值）</span><span class="sxs-lookup"><span data-stu-id="cecff-131">0 = Executable (default)</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="cecff-132">需要 ApplicationInstallPath。</span><span class="sxs-lookup"><span data-stu-id="cecff-132">Requires ApplicationInstallPath.</span></span>


</div>
<p><span data-ttu-id="cecff-133">1 = 通訊協定</span><span class="sxs-lookup"><span data-stu-id="cecff-133">1 = Protocol</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cecff-134">ApplicationInstallPath</span><span class="sxs-lookup"><span data-stu-id="cecff-134">ApplicationInstallPath</span></span></p></td>
<td><p><span data-ttu-id="cecff-135">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="cecff-135">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="cecff-136">可執行檔的完整路徑。</span><span class="sxs-lookup"><span data-stu-id="cecff-136">Full path of the executable.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="cecff-137">必須指定是否 ApplicationType 為 0 （可執行檔）。</span><span class="sxs-lookup"><span data-stu-id="cecff-137">Must be specified if ApplicationType is 0 (Executable).</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cecff-138">路徑</span><span class="sxs-lookup"><span data-stu-id="cecff-138">Path</span></span></p></td>
<td><p><span data-ttu-id="cecff-139">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="cecff-139">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="cecff-140">為與任何參數，包括預設參數<em>%使用者識別碼 %</em>和<em>%連絡人識別碼 %</em>一起啟動的完整路徑。</span><span class="sxs-lookup"><span data-stu-id="cecff-140">Full path to be started along with any parameters, including the default parameters <em>%user-id%</em> and <em>%contact-id%</em>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cecff-141">SessionType</span><span class="sxs-lookup"><span data-stu-id="cecff-141">SessionType</span></span></p></td>
<td><p><span data-ttu-id="cecff-142">DWORD</span><span class="sxs-lookup"><span data-stu-id="cecff-142">DWORD</span></span></p></td>
<td><p><span data-ttu-id="cecff-p102">0 = 本機工作階段。在本機電腦上啟動應用程式。</span><span class="sxs-lookup"><span data-stu-id="cecff-p102">0 = Local session. The application is started on the local computer.</span></span></p>
<p><span data-ttu-id="cecff-145">1 = 兩方工作階段 (預設)。</span><span class="sxs-lookup"><span data-stu-id="cecff-145">1 = Two-party session (default).</span></span> <span data-ttu-id="cecff-146">Lync 2013 啟動本機的應用程式，並再將桌面通知傳送給其他使用者。</span><span class="sxs-lookup"><span data-stu-id="cecff-146">Lync 2013 starts the application locally and then sends a desktop notification to the other user.</span></span> <span data-ttu-id="cecff-147">其他使用者點選其電腦上啟動應用程式的通知。</span><span class="sxs-lookup"><span data-stu-id="cecff-147">The other user clicks the notification to start the application on their computer.</span></span></p>
<p><span data-ttu-id="cecff-148">2 = 多方工作階段。</span><span class="sxs-lookup"><span data-stu-id="cecff-148">2 = Multiparty session.</span></span> <span data-ttu-id="cecff-149">Lync 2013 啟動本機的應用程式，並再將桌面通知傳送給其他使用者。</span><span class="sxs-lookup"><span data-stu-id="cecff-149">Lync 2013 starts the application locally and then sends desktop notifications to the other users.</span></span> <span data-ttu-id="cecff-150">其他使用者按一下通知給他們的電腦上啟動指定的應用程式。</span><span class="sxs-lookup"><span data-stu-id="cecff-150">The other user clicks the notification to start the specified application on their computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cecff-151">ExtensibleMenu</span><span class="sxs-lookup"><span data-stu-id="cecff-151">ExtensibleMenu</span></span></p></td>
<td><p><span data-ttu-id="cecff-152">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="cecff-152">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="cecff-153">此命令將會出現的位置，功能表清單以分號分隔。</span><span class="sxs-lookup"><span data-stu-id="cecff-153">A list of the menus where this command will appear, separated by semicolons.</span></span> <span data-ttu-id="cecff-154">可能的值有：</span><span class="sxs-lookup"><span data-stu-id="cecff-154">Possible values are:</span></span></p>
<p><span data-ttu-id="cecff-155">MainWindowActions</span><span class="sxs-lookup"><span data-stu-id="cecff-155">MainWindowActions</span></span></p>
<p><span data-ttu-id="cecff-156">MainWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="cecff-156">MainWindowRightClick</span></span></p>
<p><span data-ttu-id="cecff-157">ConversationWindowActions</span><span class="sxs-lookup"><span data-stu-id="cecff-157">ConversationWindowActions</span></span></p>
<p><span data-ttu-id="cecff-158">ConversationWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="cecff-158">ConversationWindowRightClick</span></span></p>
<p><span data-ttu-id="cecff-159">ContactCardMenu</span><span class="sxs-lookup"><span data-stu-id="cecff-159">ContactCardMenu</span></span></p>
<p><span data-ttu-id="cecff-160">如果沒有定義 ExtensibleMenu ，會使用 MainWindowRightClick 和 ConversationWindowActions 的預設值。</span><span class="sxs-lookup"><span data-stu-id="cecff-160">If ExtensibleMenu is not defined, the default values of MainWindowRightClick and ConversationWindowActions are used.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="cecff-161">例如，下列登錄編輯程式 (。登錄） 檔案會顯示將 Contoso Sales Contact Manager 功能表項目新增至 [交談] 視窗中的 [動作] 功能表的結果：</span><span class="sxs-lookup"><span data-stu-id="cecff-161">For example, the following Registry Editor (.REG) file shows the results of adding a Contoso Sales Contact Manager menu item to Actions menu in the Conversation window:</span></span>

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

## <a name="to-access-a-custom-command"></a><span data-ttu-id="cecff-162">若要存取自訂命令</span><span class="sxs-lookup"><span data-stu-id="cecff-162">To access a custom command</span></span>

<span data-ttu-id="cecff-163">若要存取自訂命令後就當簡報加入，執行下列命令，根據您定義的 ExtensibleMenu 值其中一項：</span><span class="sxs-lookup"><span data-stu-id="cecff-163">To access a custom command after it is added, do one of the following, depending on the ExtensibleMenu values that you define:</span></span>

  - <span data-ttu-id="cecff-164">**MainWindowActions**   在 Lync 主視窗中，按一下 [**工具**]，然後按一下 [您的自訂命令。</span><span class="sxs-lookup"><span data-stu-id="cecff-164">**MainWindowActions**   In the Lync main window, click **Tools**, and then click your custom command.</span></span>

  - <span data-ttu-id="cecff-165">**MainWindowRightClick**   在 Lync 主視窗中，以滑鼠右鍵按一下連絡人，，，然後按一下 [您的自訂命令。</span><span class="sxs-lookup"><span data-stu-id="cecff-165">**MainWindowRightClick**   In the Lync main window, right-click a contact, and then click your custom command.</span></span>

  - <span data-ttu-id="cecff-166">**ConversationWindowActions**   中 [交談] 視窗中，按一下 [**更多選項**] 圖示，然後按一下 [您的自訂命令。</span><span class="sxs-lookup"><span data-stu-id="cecff-166">**ConversationWindowActions**   In the Conversation window, click the **More Options** icon, and then click your custom command.</span></span>

  - <span data-ttu-id="cecff-167">**ConversationWindowRightClick**   在 [交談] 視窗中，以滑鼠右鍵按一下連絡人名稱，，，然後按一下 [您的自訂命令。</span><span class="sxs-lookup"><span data-stu-id="cecff-167">**ConversationWindowRightClick**   In the Conversation window, right-click a contact name, and then click your custom command.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

