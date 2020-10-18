---
title: 建立或修改 Lync Phone Edition 配置設定的集合
description: 建立或修改 Lync Phone Edition 配置設定的集合。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of Lync Phone Edition configuration settings
ms:assetid: 6cf714af-8f57-4a71-89ad-0a776302b2ba
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688086(v=OCS.15)
ms:contentKeyID: 49733683
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82a4becadf581ec965952e507c3eb2839b622d9f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578249"
---
# <a name="create-or-modify-a-collection-of-lync-phone-edition-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="d02a3-103">在 Lync Server 2013 中建立或修改 Lync Phone Edition 設定的集合</span><span class="sxs-lookup"><span data-stu-id="d02a3-103">Create or modify a collection of Lync Phone Edition configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d02a3-104">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="d02a3-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="d02a3-105">當您安裝 Lync Server 時，會取得「Lync Phone Edition」設定的全域集合。</span><span class="sxs-lookup"><span data-stu-id="d02a3-105">When you install Lync Server, you get a global collection of Lync Phone Edition settings.</span></span> <span data-ttu-id="d02a3-106">這些設定會套用至部署中所有執行 Lync Phone Edition 的裝置。</span><span class="sxs-lookup"><span data-stu-id="d02a3-106">These settings apply to all devices running Lync Phone Edition in your deployment.</span></span> <span data-ttu-id="d02a3-107">您可以隨時變更這些設定。</span><span class="sxs-lookup"><span data-stu-id="d02a3-107">You can change these settings at any time.</span></span> <span data-ttu-id="d02a3-108">您也可以設定套用至特定網站中裝置的新設定集合。</span><span class="sxs-lookup"><span data-stu-id="d02a3-108">You can also set up a new collection of settings that apply to the devices in a specific site.</span></span> <span data-ttu-id="d02a3-109">網站設定的優先順序高於全域設定。</span><span class="sxs-lookup"><span data-stu-id="d02a3-109">Site settings take precedence over global settings.</span></span>

<span data-ttu-id="d02a3-110">組態設定包含集合名稱、範圍 (全域或網站)、SIP 安全性設定、記錄層次、語音服務品質 (QoS) 層級、電話鎖定設定與電話鎖定詳細資料，即 a) 個人識別碼 (PIN) 的解除鎖定時間必須為多久，以及 b) 電話自行鎖定前的閒置時間為多久。</span><span class="sxs-lookup"><span data-stu-id="d02a3-110">Configuration settings consist of the collection name, scope (global or site), SIP security setting, logging level, voice quality of service (QoS) level, phone-lock setting, and phone-lock details, that is, how long the a) unlock personal identification number (PIN) must be and b) phone stays idle before locking itself.</span></span>

<div>

## <a name="to-create-a-collection-of-lync-phone-edition-configuration-settings-or-edit-settings-for-an-existing-collection"></a><span data-ttu-id="d02a3-111">若要建立 Lync Phone Edition 設定的集合，或編輯現有集合的設定</span><span class="sxs-lookup"><span data-stu-id="d02a3-111">To create a collection of Lync Phone Edition configuration settings or edit settings for an existing collection</span></span>

1.  <span data-ttu-id="d02a3-112">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="d02a3-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d02a3-113">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="d02a3-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d02a3-114">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="d02a3-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d02a3-115">在左導覽列中，按一下 **[用戶端]**，然後再按一下 **[裝置組態]** 導覽按鈕。</span><span class="sxs-lookup"><span data-stu-id="d02a3-115">In the left navigation bar, click **Clients**, and then click the **Device Configuration** navigation button.</span></span>

4.  <span data-ttu-id="d02a3-116">在 **[裝置組態]** 頁面上，執行下列其中一項作業：</span><span class="sxs-lookup"><span data-stu-id="d02a3-116">On the **Device Configuration** page, do one of the following:</span></span>
    
      - <span data-ttu-id="d02a3-117">若要建立新的 Lync Phone Edition 設定的集合，請依序按一下 [ **新增**] 及 **[網站]，按一下 [確定]**，複查預設設定，如果您想要的話，請進行任何變更。</span><span class="sxs-lookup"><span data-stu-id="d02a3-117">To create a new collection of Lync Phone Edition configuration settings, click **New**, select a site, click **OK**, review the default settings, and, if you want to, make any changes.</span></span>
    
      - <span data-ttu-id="d02a3-118">若要在現有集合中編輯任何設定，請依序按一下集合、**[編輯]** 功能表、**[顯示詳細資料]**，然後進行變更。</span><span class="sxs-lookup"><span data-stu-id="d02a3-118">To edit any of the settings in an existing collection, click the collection, click the **Edit** menu, click **Show details**, and then make your changes.</span></span>
        
        <div>
        

        > [!TIP]
        > <span data-ttu-id="d02a3-p103">若要返回以使用全域集合的預設設定，請依序按一下全域集合、<STRONG>[編輯]</STRONG>功能表、<STRONG>[刪除]</STRONG>，然後按一下 <STRONG>[確定]</STRONG>。這樣做並不會刪除全域集合，只是將設定重設為預設值。</span><span class="sxs-lookup"><span data-stu-id="d02a3-p103">To go back to using the default settings for the global collection, click the global collection, click the <STRONG>Edit</STRONG> menu, click <STRONG>Delete</STRONG>, and then click <STRONG>OK</STRONG>. This will not delete the global collection; it just resets the settings to the defaults.</span></span>

        
        </div>

5.  <span data-ttu-id="d02a3-121">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="d02a3-121">Click **Commit**.</span></span>

</div>

<div>

## <a name="creating-new-lync-phone-edition-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="d02a3-122">使用 Windows PowerShell Cmdlet 建立新的 Lync Phone Edition 配置設定</span><span class="sxs-lookup"><span data-stu-id="d02a3-122">Creating New Lync Phone Edition Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="d02a3-123">您可以在網站範圍內 (，只) 使用 Windows PowerShell 和 **New-CsUCPhoneConfiguration** Cmdlet 來建立 Lync Phone Edition 的設定。</span><span class="sxs-lookup"><span data-stu-id="d02a3-123">You can create Lync Phone Edition configuration settings can (at the site scope only) by using Windows PowerShell and the **New-CsUCPhoneConfiguration** cmdlet.</span></span> <span data-ttu-id="d02a3-124">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d02a3-124">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="d02a3-125">如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="d02a3-125">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-new-lync-phone-edition-configuration-settings-that-use-the-default-values"></a><span data-ttu-id="d02a3-126">若要建立新的 Lync Phone Edition 設定，使用預設值</span><span class="sxs-lookup"><span data-stu-id="d02a3-126">To create new Lync Phone Edition configuration settings that use the default values</span></span>

  - <span data-ttu-id="d02a3-127">這個命令會針對 Redmond 網站建立一組新的 UC 電話組態設定：</span><span class="sxs-lookup"><span data-stu-id="d02a3-127">This command creates a new set of UC phone configuration settings for the Redmond site:</span></span>
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond"
    
    <span data-ttu-id="d02a3-128">由於以上的命令未指定任何參數 (強制的 Identity 參數除外)，新的組態設定集合將針對其所有屬性使用預設值。</span><span class="sxs-lookup"><span data-stu-id="d02a3-128">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties.</span></span>

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-new-lync-phone-edition-configuration-settings"></a><span data-ttu-id="d02a3-129">在建立新的 Lync Phone Edition 配置設定時變更單一屬性值</span><span class="sxs-lookup"><span data-stu-id="d02a3-129">To change a single property value when creating new Lync Phone Edition configuration settings</span></span>

  - <span data-ttu-id="d02a3-p105">若要建立使用不同屬性質的設定，只需要加入適當的參數和參數值即可。例如，若要建立 UC 電話組態設定的集合，根據預設，需要執行電話鎖定，您可以使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="d02a3-p105">To create settings that use different property values, simply include the appropriate parameter and parameter value. For example, to create a collection of UC phone configuration settings that, by default, require phone locking, use a command like this:</span></span>
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond" -EnforcePhoneLock $True

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-new-lync-phone-edition-configuration-settings"></a><span data-ttu-id="d02a3-132">在建立新的 Lync Phone Edition 配置設定時變更多個屬性值</span><span class="sxs-lookup"><span data-stu-id="d02a3-132">To change multiple property values when creating new Lync Phone Edition configuration settings</span></span>

  - <span data-ttu-id="d02a3-p106">多項屬性值可透過加入多個參數加以修改。例如，這個命令會強制執行電話鎖定，也會將最小 PIN 長度限制設為 8 位數：</span><span class="sxs-lookup"><span data-stu-id="d02a3-p106">Multiple property values can be modified by including multiple parameters. For example, this command enforces phone locking and also sets the minimum PIN length to 8 digits:</span></span>
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond" -EnforcePhoneLock $True -MinPhonePinLength 8

</div>

<span data-ttu-id="d02a3-135">如需詳細資訊，請參閱 [New-CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg398445(v=OCS.15))。</span><span class="sxs-lookup"><span data-stu-id="d02a3-135">For details, see [New-CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg398445(v=OCS.15)).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d02a3-136">另請參閱</span><span class="sxs-lookup"><span data-stu-id="d02a3-136">See Also</span></span>


[<span data-ttu-id="d02a3-137">在 Lync Server 2013 中刪除現有的 Lync Phone Edition 配置設定集合</span><span class="sxs-lookup"><span data-stu-id="d02a3-137">Delete an existing collection of Lync Phone Edition configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-lync-phone-edition-configuration-settings.md)  
[<span data-ttu-id="d02a3-138">在 Lync Server 2013 中設定 Lync Phone Edition 的安全性設定</span><span class="sxs-lookup"><span data-stu-id="d02a3-138">Configure security settings for Lync Phone Edition in Lync Server 2013</span></span>](lync-server-2013-configure-security-settings-for-lync-phone-edition.md)  
[<span data-ttu-id="d02a3-139">在 Lync Server 2013 中強制執行電話鎖定</span><span class="sxs-lookup"><span data-stu-id="d02a3-139">Enforce phone locking in Lync Server 2013</span></span>](lync-server-2013-enforce-phone-locking.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

