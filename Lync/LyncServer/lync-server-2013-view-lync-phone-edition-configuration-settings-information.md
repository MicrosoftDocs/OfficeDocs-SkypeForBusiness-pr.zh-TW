---
title: Lync Server 2013：查看 Lync 手機版設定資訊
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View Lync Phone Edition configuration settings information
ms:assetid: 15f94478-651f-4063-9918-6a059f98df16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687976(v=OCS.15)
ms:contentKeyID: 49733564
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 213b9775b22818c34eb8f7896ea02a4872182a42
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978331"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-lync-phone-edition-configuration-settings-information-in-lync-server-2013"></a><span data-ttu-id="452a7-102">在 Lync Server 2013 中查看 Lync 手機版設定資訊</span><span class="sxs-lookup"><span data-stu-id="452a7-102">View Lync Phone Edition configuration settings information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="452a7-103">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="452a7-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="452a7-104">您可以查看執行 Lync Phone Edition 的裝置設定資訊。</span><span class="sxs-lookup"><span data-stu-id="452a7-104">You can view configuration information about devices running Lync Phone Edition.</span></span> <span data-ttu-id="452a7-105">資訊會組織成集合。</span><span class="sxs-lookup"><span data-stu-id="452a7-105">The information is organized into collections.</span></span> <span data-ttu-id="452a7-106">當您安裝 Lync Server 時，您會取得 Lync 手機版設定的集合，該集合會套用至您在部署中執行 Lync 手機版本的所有裝置。</span><span class="sxs-lookup"><span data-stu-id="452a7-106">When you install Lync Server, you get a collection of Lync Phone Edition settings that apply to all the devices running Lync Phone Edition in your deployment.</span></span> <span data-ttu-id="452a7-107">您也可以為特定網站建立新的設定集合。</span><span class="sxs-lookup"><span data-stu-id="452a7-107">You can also create new collections of settings for a specific site.</span></span> <span data-ttu-id="452a7-108">[網站設定] 優先于 [全域設定]。</span><span class="sxs-lookup"><span data-stu-id="452a7-108">Site settings take precedence over global settings.</span></span> <span data-ttu-id="452a7-109">每個設定集合都包含一個名稱、範圍（全域或網站）、SIP 安全性設定、記錄層級、語音服務品質（QoS）等級、電話鎖定設定，以及電話鎖定詳細資料，也就是解除鎖定個人身分識別的最小長度電話號碼（PIN）與電話鎖定本身之前的時間。</span><span class="sxs-lookup"><span data-stu-id="452a7-109">Each collection of settings consists of a name, the scope (global or site), SIP security setting, logging level, voice quality of service (QoS) level, phone-lock setting, and phone-lock details, that is, the minimum length of the unlock personal identification number (PIN) and time before the phone locks itself.</span></span>

<div>

## <a name="to-view-configuration-information-about-devices-running-lync-phone-edition"></a><span data-ttu-id="452a7-110">若要查看執行 Lync Phone Edition 之裝置的設定資訊</span><span class="sxs-lookup"><span data-stu-id="452a7-110">To view configuration information about devices running Lync Phone Edition</span></span>

1.  <span data-ttu-id="452a7-111">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="452a7-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="452a7-112">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="452a7-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="452a7-113">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="452a7-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="452a7-114">在左側導覽列中，按一下 [**用戶端**]，然後按一下 [**裝置配置**] 瀏覽按鈕。</span><span class="sxs-lookup"><span data-stu-id="452a7-114">In the left navigation bar, click **Clients**, and then click the **Device Configuration** navigation button.</span></span>

4.  <span data-ttu-id="452a7-115">在 [**裝置**設定] 頁面上，按一下您要用來查看相關資訊的設定集合。</span><span class="sxs-lookup"><span data-stu-id="452a7-115">On the **Device Configuration** page, click the collection of settings you want to view information about.</span></span> <span data-ttu-id="452a7-116">[名稱]、[範圍]、[SIP 安全性] 設定、[語音品質] 層級及 [電話封鎖] 設定會列在主版頁面上。</span><span class="sxs-lookup"><span data-stu-id="452a7-116">The name, scope, SIP security setting, voice quality level, and phone lock setting are listed on the main page.</span></span> <span data-ttu-id="452a7-117">若要查看記錄層級和電話鎖定的詳細資料，請按一下 [**編輯**] 功能表，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="452a7-117">To view the logging level and phone lock details, click the **Edit** menu, and then click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-lync-phone-edition-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="452a7-118">使用 Windows PowerShell Cmdlet 來查看 Lync 手機版配置資訊</span><span class="sxs-lookup"><span data-stu-id="452a7-118">Viewing Lync Phone Edition Configuration Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="452a7-119">您可以使用 Lync Server 管理命令介面和**CsUCPhoneConfiguration** Cmdlet 來查看 Lync 手機版設定設定。</span><span class="sxs-lookup"><span data-stu-id="452a7-119">You can view Lync Phone Edition configuration settings by using Lync Server Management Shell and the **Get-CsUCPhoneConfiguration** cmdlet.</span></span> <span data-ttu-id="452a7-120">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="452a7-120">You can run this cmdlet can from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="452a7-121">如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="452a7-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-lync-phone-edition-configuration-information"></a><span data-ttu-id="452a7-122">若要查看 Lync 手機版本設定資訊</span><span class="sxs-lookup"><span data-stu-id="452a7-122">To view Lync Phone Edition configuration information</span></span>

  - <span data-ttu-id="452a7-123">若要查看所有 Lync Phone Edition 設定設定的相關資訊，請在 Lync Server 管理命令介面中輸入下列命令，然後按 ENTER 鍵：</span><span class="sxs-lookup"><span data-stu-id="452a7-123">To view information about all your Lync Phone Edition configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsUCPhoneConfiguration
    
    <span data-ttu-id="452a7-124">此命令會傳回如下所示的資訊：</span><span class="sxs-lookup"><span data-stu-id="452a7-124">The command returns information similar to the following:</span></span>
    
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

<span data-ttu-id="452a7-125">如需詳細資訊，請參閱[CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration)。</span><span class="sxs-lookup"><span data-stu-id="452a7-125">For details, see [Get-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="452a7-126">請參閱</span><span class="sxs-lookup"><span data-stu-id="452a7-126">See Also</span></span>


[<span data-ttu-id="452a7-127">在 Lync Server 2013 中建立或修改 Lync 手機版配置設定的集合</span><span class="sxs-lookup"><span data-stu-id="452a7-127">Create or modify a collection of Lync Phone Edition configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md)  
[<span data-ttu-id="452a7-128">刪除 Lync Server 2013 中現有的 Lync Phone Edition 配置設定集合</span><span class="sxs-lookup"><span data-stu-id="452a7-128">Delete an existing collection of Lync Phone Edition configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-lync-phone-edition-configuration-settings.md)  
[<span data-ttu-id="452a7-129">在 Lync Server 2013 中設定 Lync Phone Edition 的安全性設定</span><span class="sxs-lookup"><span data-stu-id="452a7-129">Configure security settings for Lync Phone Edition in Lync Server 2013</span></span>](lync-server-2013-configure-security-settings-for-lync-phone-edition.md)  
[<span data-ttu-id="452a7-130">在 Lync Server 2013 中強制執行電話鎖定</span><span class="sxs-lookup"><span data-stu-id="452a7-130">Enforce phone locking in Lync Server 2013</span></span>](lync-server-2013-enforce-phone-locking.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

