---
title: Lync Server 2013：查看 Lync Phone Edition 設定資訊
description: Lync Server 2013：查看 Lync Phone Edition 設定資訊。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View Lync Phone Edition configuration settings information
ms:assetid: 15f94478-651f-4063-9918-6a059f98df16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687976(v=OCS.15)
ms:contentKeyID: 49733564
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 62719b24920ee72a92b2f80498d5ea2a59288c2e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576429"
---
# <a name="view-lync-phone-edition-configuration-settings-information-in-lync-server-2013"></a><span data-ttu-id="6ec01-103">在 Lync Server 2013 中查看 Lync Phone Edition 設定資訊</span><span class="sxs-lookup"><span data-stu-id="6ec01-103">View Lync Phone Edition configuration settings information in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6ec01-104">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="6ec01-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="6ec01-105">您可以查看有關執行 Lync Phone Edition 之裝置的設定資訊。</span><span class="sxs-lookup"><span data-stu-id="6ec01-105">You can view configuration information about devices running Lync Phone Edition.</span></span> <span data-ttu-id="6ec01-106">此資訊會組織成集合。</span><span class="sxs-lookup"><span data-stu-id="6ec01-106">The information is organized into collections.</span></span> <span data-ttu-id="6ec01-107">當您安裝 Lync Server 時，會取得 Lync Phone Edition 設定的集合，這些設定會套用至部署中所有執行 Lync Phone Edition 的裝置。</span><span class="sxs-lookup"><span data-stu-id="6ec01-107">When you install Lync Server, you get a collection of Lync Phone Edition settings that apply to all the devices running Lync Phone Edition in your deployment.</span></span> <span data-ttu-id="6ec01-108">您也可以針對特定網站建立新的設定集合。</span><span class="sxs-lookup"><span data-stu-id="6ec01-108">You can also create new collections of settings for a specific site.</span></span> <span data-ttu-id="6ec01-109">網站設定的優先順序高於全域設定。</span><span class="sxs-lookup"><span data-stu-id="6ec01-109">Site settings take precedence over global settings.</span></span> <span data-ttu-id="6ec01-110">每個設定集合都包含名稱、範圍 (全域或網站)、SIP 安全性設定、記錄層級、語音服務品質 (QoS) 層級、電話鎖定設定以及電話鎖定詳細資料 (也就是解除鎖定個人識別碼 (PIN) 的長度下限，以及電話自我鎖定之前的時間)。</span><span class="sxs-lookup"><span data-stu-id="6ec01-110">Each collection of settings consists of a name, the scope (global or site), SIP security setting, logging level, voice quality of service (QoS) level, phone-lock setting, and phone-lock details, that is, the minimum length of the unlock personal identification number (PIN) and time before the phone locks itself.</span></span>

<div>

## <a name="to-view-configuration-information-about-devices-running-lync-phone-edition"></a><span data-ttu-id="6ec01-111">若要查看有關執行 Lync Phone Edition 之裝置的設定資訊</span><span class="sxs-lookup"><span data-stu-id="6ec01-111">To view configuration information about devices running Lync Phone Edition</span></span>

1.  <span data-ttu-id="6ec01-112">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="6ec01-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="6ec01-113">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="6ec01-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="6ec01-114">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="6ec01-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="6ec01-115">在左導覽列中，按一下 [用戶端]\*\*\*\*，然後按一下 [裝置設定]\*\*\*\* 導覽按鈕。</span><span class="sxs-lookup"><span data-stu-id="6ec01-115">In the left navigation bar, click **Clients**, and then click the **Device Configuration** navigation button.</span></span>

4.  <span data-ttu-id="6ec01-p103">在「裝置設定」\*\*\*\* 頁面上，按一下您要檢視其相關資訊的設定集合。名稱、範圍、SIP 安全性設定、語音品質層級及電話鎖定設定會列示在主要頁面上。若要檢視記錄層級和電話鎖定詳細資料，請按一下 [編輯]\*\*\*\* 功能表，然後按一下 [顯示詳細資料]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6ec01-p103">On the **Device Configuration** page, click the collection of settings you want to view information about. The name, scope, SIP security setting, voice quality level, and phone lock setting are listed on the main page. To view the logging level and phone lock details, click the **Edit** menu, and then click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-lync-phone-edition-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="6ec01-119">使用 Windows PowerShell Cmdlet 來查看 Lync Phone Edition 設定資訊</span><span class="sxs-lookup"><span data-stu-id="6ec01-119">Viewing Lync Phone Edition Configuration Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="6ec01-120">您可以使用 Lync Server 管理命令介面和 **Get-CsUCPhoneConfiguration** Cmdlet 來查看 Lync Phone Edition 的設定設定。</span><span class="sxs-lookup"><span data-stu-id="6ec01-120">You can view Lync Phone Edition configuration settings by using Lync Server Management Shell and the **Get-CsUCPhoneConfiguration** cmdlet.</span></span> <span data-ttu-id="6ec01-121">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="6ec01-121">You can run this cmdlet can from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="6ec01-122">如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="6ec01-122">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-lync-phone-edition-configuration-information"></a><span data-ttu-id="6ec01-123">若要查看 Lync Phone Edition 設定資訊</span><span class="sxs-lookup"><span data-stu-id="6ec01-123">To view Lync Phone Edition configuration information</span></span>

  - <span data-ttu-id="6ec01-124">若要查看所有 Lync Phone Edition 設定設定的相關資訊，請在 Lync Server 管理命令介面中輸入下列命令，然後按 ENTER：</span><span class="sxs-lookup"><span data-stu-id="6ec01-124">To view information about all your Lync Phone Edition configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsUCPhoneConfiguration
    
    <span data-ttu-id="6ec01-125">該命令會傳回如下資訊：</span><span class="sxs-lookup"><span data-stu-id="6ec01-125">The command returns information similar to the following:</span></span>
    
        Identity             : Global
        CalendarPollInterval : 00:03:00
        EnforcePhoneLock     : True
        PhoneLockTimeout     : 00:10:00
        MinPhonePinLength    : 6
        SIPSecurityMode      : High
        VoiceDiffServTag     : 40
        Voice8021p           : 0
        LoggingLevel         : Off

</div>

<span data-ttu-id="6ec01-126">如需詳細資訊，請參閱 [Get-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration)。</span><span class="sxs-lookup"><span data-stu-id="6ec01-126">For details, see [Get-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6ec01-127">另請參閱</span><span class="sxs-lookup"><span data-stu-id="6ec01-127">See Also</span></span>


[<span data-ttu-id="6ec01-128">在 Lync Server 2013 中建立或修改 Lync Phone Edition 設定的集合</span><span class="sxs-lookup"><span data-stu-id="6ec01-128">Create or modify a collection of Lync Phone Edition configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md)  
[<span data-ttu-id="6ec01-129">在 Lync Server 2013 中刪除現有的 Lync Phone Edition 配置設定集合</span><span class="sxs-lookup"><span data-stu-id="6ec01-129">Delete an existing collection of Lync Phone Edition configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-lync-phone-edition-configuration-settings.md)  
[<span data-ttu-id="6ec01-130">在 Lync Server 2013 中設定 Lync Phone Edition 的安全性設定</span><span class="sxs-lookup"><span data-stu-id="6ec01-130">Configure security settings for Lync Phone Edition in Lync Server 2013</span></span>](lync-server-2013-configure-security-settings-for-lync-phone-edition.md)  
[<span data-ttu-id="6ec01-131">在 Lync Server 2013 中強制執行電話鎖定</span><span class="sxs-lookup"><span data-stu-id="6ec01-131">Enforce phone locking in Lync Server 2013</span></span>](lync-server-2013-enforce-phone-locking.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

