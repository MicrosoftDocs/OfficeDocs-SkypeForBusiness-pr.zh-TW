---
title: 修改未明確支援或限制之用戶端的預設動作
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify the default action for clients not explicitly supported or restricted
ms:assetid: 548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520994(v=OCS.15)
ms:contentKeyID: 48184137
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 213e42a7477202cf40a0b06c79edde49976f0bbc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515270"
---
# <a name="modify-the-default-action-for-clients-not-explicitly-supported-or-restricted-in-lync-server-2013"></a><span data-ttu-id="bb6aa-102">在 Lync Server 2013 中修改未明確支援或限制之用戶端的預設動作</span><span class="sxs-lookup"><span data-stu-id="bb6aa-102">Modify the default action for clients not explicitly supported or restricted in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bb6aa-103">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="bb6aa-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="bb6aa-104">除了指定您要在 Lync Server 2013 環境中支援的用戶端版本之外，您也可以針對尚未定義版本原則的用戶端，指定預設動作。</span><span class="sxs-lookup"><span data-stu-id="bb6aa-104">In addition to specifying the version of clients that you want to support in your Lync Server 2013 environment, you can also specify a default action for clients that do not already have a version policy defined.</span></span> <span data-ttu-id="bb6aa-105">這可讓您限制 Lync Server 環境中所使用的用戶端版本，這可協助您控制支援多個用戶端版本的相關成本。</span><span class="sxs-lookup"><span data-stu-id="bb6aa-105">This enables you to restrict which client versions are used in your Lync Server environment, which can help you control the costs associated with supporting multiple client versions.</span></span>

<div>

## <a name="to-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted"></a><span data-ttu-id="bb6aa-106">若要針對沒有明確支援或限制的用戶端修改其預設動作</span><span class="sxs-lookup"><span data-stu-id="bb6aa-106">To modify the default action for clients not explicitly supported or restricted</span></span>

1.  <span data-ttu-id="bb6aa-107">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="bb6aa-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="bb6aa-108">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="bb6aa-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="bb6aa-109">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="bb6aa-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="bb6aa-110">在左導覽列中，依序按一下 **[用戶端]**、**[用戶端版本設定]**。</span><span class="sxs-lookup"><span data-stu-id="bb6aa-110">In the left navigation bar, click **Clients**, and then click **Client Version Configuration**.</span></span>

4.  <span data-ttu-id="bb6aa-111">在 **[用戶端版本設定]** 頁面上，按兩下清單裡的 **[通用]** 組態。</span><span class="sxs-lookup"><span data-stu-id="bb6aa-111">On the **Client Version Configuration** page, double-click the **Global** configuration in the list.</span></span>

5.  <span data-ttu-id="bb6aa-112">在 **[編輯用戶端版本設定]** 對話方塊中，確認 **[啟用版本控制]** 核取方塊已經選取，然後在 **[預設動作]** 下方，選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="bb6aa-112">In the **Edit Client Version Configuration** dialog box, verify that the **Enable version control** check box is selected and then, under **Default action**, select one of the following:</span></span>
    
      - <span data-ttu-id="bb6aa-113">**允許**    當用戶端版本不符合**用戶端版本原則**清單中的任何篩選準則時，允許用戶端登入。</span><span class="sxs-lookup"><span data-stu-id="bb6aa-113">**Allow**   Allows the client to log on if the client version does not match any filter in the **Client version policies** list.</span></span>
    
      - <span data-ttu-id="bb6aa-114">**封鎖**    當用戶端版本不符合**用戶端版本原則**清單中的任何篩選準則時，禁止用戶端登入。</span><span class="sxs-lookup"><span data-stu-id="bb6aa-114">**Block**   Prevents the client from logging on if the client version does not match any filter in the **Client version policies** list.</span></span>
    
      - <span data-ttu-id="bb6aa-115">**使用 URL**     的封鎖當用戶端版本不符合**用戶端版本原則**清單中的任何篩選準則時，禁止用戶端登入，並包含包含 URL 的錯誤訊息，可供下載更新的用戶端。</span><span class="sxs-lookup"><span data-stu-id="bb6aa-115">**Block with URL**   Prevents the client from logging on if the client version does not match any filter in the **Client version policies** list, and include an error message containing a URL where a newer client can be downloaded.</span></span>
    
      - <span data-ttu-id="bb6aa-116">**允許搭配 URL**    當用戶端版本不符合**用戶端版本原則**清單中的任何篩選準則時，允許用戶端登入，並包含包含可下載更新之用戶端的 URL 的錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="bb6aa-116">**Allow with URL**   Allows the client to log on if the client version does not match any filter in the **Client version policies** list, and include an error message containing a URL where a newer client can be downloaded.</span></span>

6.  <span data-ttu-id="bb6aa-117">如果您選取 **[以 URL 封鎖]**，請輸入要包含在錯誤訊息中 **[URL]** 方塊的用戶端下載 URL。</span><span class="sxs-lookup"><span data-stu-id="bb6aa-117">If you selected **Block with URL**, type the client download URL to include in the error message in the **URL** box.</span></span>

7.  <span data-ttu-id="bb6aa-118">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="bb6aa-118">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-disable-client-version-control"></a><span data-ttu-id="bb6aa-119">若要停用用戶端版本控制</span><span class="sxs-lookup"><span data-stu-id="bb6aa-119">To disable client version control</span></span>

  - <span data-ttu-id="bb6aa-120">若要停用版本控制以允許所有用戶端使用任何用戶端版本登入，請清除 **[啟用版本控制]** 核取方塊，然後按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="bb6aa-120">To disable version control to allow all clients to log on regardless of the client version, clear the **Enable version control** check box, and then click **Commit**.</span></span>

</div>

<div>

## <a name="modifying-the-default-action-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="bb6aa-121">使用 Windows PowerShell Cmdlet 修改預設動作</span><span class="sxs-lookup"><span data-stu-id="bb6aa-121">Modifying the Default Action by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="bb6aa-122">當使用者嘗試使用未明確支援或受用戶端版本原則限制之用戶端進行登入時所採取的預設動作，可使用 Windows PowerShell 命令列介面和 **Set-CsClientVersionPolicy** Cmdlet 來管理。</span><span class="sxs-lookup"><span data-stu-id="bb6aa-122">The default action to be taken when users try to sign on using clients that are not explicitly supported or restricted by a client version policy can be managed by using Windows PowerShell command-line interface and the **Set-CsClientVersionPolicy** cmdlet.</span></span> <span data-ttu-id="bb6aa-123">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="bb6aa-123">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="bb6aa-124">如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="bb6aa-124">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-configure-the-default-action-to-block-access"></a><span data-ttu-id="bb6aa-125">設定預設動作以封鎖存取</span><span class="sxs-lookup"><span data-stu-id="bb6aa-125">To configure the default action to block access</span></span>

  - <span data-ttu-id="bb6aa-p104">下列命令會將 Redmond 網站的預設動作設定為 [封鎖]。這將會封鎖任何未包含用戶端版本設定規則之用戶端的登錄。</span><span class="sxs-lookup"><span data-stu-id="bb6aa-p104">The following command sets the default action for the Redmond site Block. This will block registration for any client for which no client version configuration rule exists.</span></span>
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -DefaultAction Block

</div>

<div>

## <a name="to-configure-the-default-action-to-allow-access"></a><span data-ttu-id="bb6aa-128">設定預設動作以允許存取</span><span class="sxs-lookup"><span data-stu-id="bb6aa-128">To configure the default action to allow access</span></span>

  - <span data-ttu-id="bb6aa-p105">在此範例中，會將 Redmond 網站的預設動作設定為 [允許]。這將會允許任何未包含用戶端版本設定規則之用戶端的登錄。</span><span class="sxs-lookup"><span data-stu-id="bb6aa-p105">In this example, the default action for the Redmond site is set to Allow. This will allow registration for any client for which no client version configuration rule exists.</span></span>
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -DefaultAction Allow

</div>

<span data-ttu-id="bb6aa-131">如需詳細資訊，請參閱 [Set-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg398876(v=OCS.15)) Cmdlet 的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="bb6aa-131">For details, see the Help topic for the [Set-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg398876(v=OCS.15)) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bb6aa-132">另請參閱</span><span class="sxs-lookup"><span data-stu-id="bb6aa-132">See Also</span></span>


[<span data-ttu-id="bb6aa-133">在 Lync Server 2013 中管理裝置、電話及用戶端應用程式</span><span class="sxs-lookup"><span data-stu-id="bb6aa-133">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

