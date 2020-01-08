---
title: 建立或修改 Lync 手機版配置設定的集合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a collection of Lync Phone Edition configuration settings
ms:assetid: 6cf714af-8f57-4a71-89ad-0a776302b2ba
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688086(v=OCS.15)
ms:contentKeyID: 49733683
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f3012ffeeb8dd4559ee05a45dd07becefd099691
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977172"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-lync-phone-edition-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="8ac20-102">在 Lync Server 2013 中建立或修改 Lync 手機版配置設定的集合</span><span class="sxs-lookup"><span data-stu-id="8ac20-102">Create or modify a collection of Lync Phone Edition configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8ac20-103">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="8ac20-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="8ac20-104">當您安裝 Lync Server 時，您會看到一組「Lync Phone Edition」設定的全域集合。</span><span class="sxs-lookup"><span data-stu-id="8ac20-104">When you install Lync Server, you get a global collection of Lync Phone Edition settings.</span></span> <span data-ttu-id="8ac20-105">這些設定適用于在您的部署中執行 Lync Phone Edition 的所有裝置。</span><span class="sxs-lookup"><span data-stu-id="8ac20-105">These settings apply to all devices running Lync Phone Edition in your deployment.</span></span> <span data-ttu-id="8ac20-106">您可以隨時變更這些設定。</span><span class="sxs-lookup"><span data-stu-id="8ac20-106">You can change these settings at any time.</span></span> <span data-ttu-id="8ac20-107">您也可以設定套用至特定網站中裝置的新設定集合。</span><span class="sxs-lookup"><span data-stu-id="8ac20-107">You can also set up a new collection of settings that apply to the devices in a specific site.</span></span> <span data-ttu-id="8ac20-108">[網站設定] 優先于 [全域設定]。</span><span class="sxs-lookup"><span data-stu-id="8ac20-108">Site settings take precedence over global settings.</span></span>

<span data-ttu-id="8ac20-109">配置設定是由集合名稱、範圍（全域或網站）、SIP 安全性設定、記錄層級、語音服務品質（QoS）等級、電話封鎖設定和電話鎖定的詳細資料所組成（也就是 a）解除鎖定個人識別碼的時間（PIN）必須是與 b 的電話，才能自行鎖定。</span><span class="sxs-lookup"><span data-stu-id="8ac20-109">Configuration settings consist of the collection name, scope (global or site), SIP security setting, logging level, voice quality of service (QoS) level, phone-lock setting, and phone-lock details, that is, how long the a) unlock personal identification number (PIN) must be and b) phone stays idle before locking itself.</span></span>

<div>

## <a name="to-create-a-collection-of-lync-phone-edition-configuration-settings-or-edit-settings-for-an-existing-collection"></a><span data-ttu-id="8ac20-110">若要建立 Lync Phone Edition 配置設定的集合，或編輯現有收藏的設定</span><span class="sxs-lookup"><span data-stu-id="8ac20-110">To create a collection of Lync Phone Edition configuration settings or edit settings for an existing collection</span></span>

1.  <span data-ttu-id="8ac20-111">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="8ac20-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="8ac20-112">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="8ac20-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="8ac20-113">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="8ac20-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="8ac20-114">在左側導覽列中，按一下 [**用戶端**]，然後按一下 [**裝置配置**] 瀏覽按鈕。</span><span class="sxs-lookup"><span data-stu-id="8ac20-114">In the left navigation bar, click **Clients**, and then click the **Device Configuration** navigation button.</span></span>

4.  <span data-ttu-id="8ac20-115">在 [**裝置**設定] 頁面上，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="8ac20-115">On the **Device Configuration** page, do one of the following:</span></span>
    
      - <span data-ttu-id="8ac20-116">若要建立新的 Lync 手機版本設定，請按一下 [**新增**]，選取一個網站，按一下 **[確定]**，查看預設設定，並視需要進行變更。</span><span class="sxs-lookup"><span data-stu-id="8ac20-116">To create a new collection of Lync Phone Edition configuration settings, click **New**, select a site, click **OK**, review the default settings, and, if you want to, make any changes.</span></span>
    
      - <span data-ttu-id="8ac20-117">若要編輯現有集合中的任何設定，請按一下該集合，按一下 [**編輯**] 功能表，按一下 [**顯示詳細資料**]，然後進行您要的變更。</span><span class="sxs-lookup"><span data-stu-id="8ac20-117">To edit any of the settings in an existing collection, click the collection, click the **Edit** menu, click **Show details**, and then make your changes.</span></span>
        
        <div>
        

        > [!TIP]
        > <span data-ttu-id="8ac20-118">若要返回使用全域集合的預設設定，請按一下全域集合，按一下 [<STRONG>編輯</STRONG>] 功能表，按一下 [<STRONG>刪除</STRONG>]，然後按一下<STRONG>[確定]</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="8ac20-118">To go back to using the default settings for the global collection, click the global collection, click the <STRONG>Edit</STRONG> menu, click <STRONG>Delete</STRONG>, and then click <STRONG>OK</STRONG>.</span></span> <span data-ttu-id="8ac20-119">這不會刪除全域集合;它只會將設定重設為預設值。</span><span class="sxs-lookup"><span data-stu-id="8ac20-119">This will not delete the global collection; it just resets the settings to the defaults.</span></span>

        
        </div>

5.  <span data-ttu-id="8ac20-120">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8ac20-120">Click **Commit**.</span></span>

</div>

<div>

## <a name="creating-new-lync-phone-edition-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="8ac20-121">使用 Windows PowerShell Cmdlet 來建立新的 Lync 手機版配置設定</span><span class="sxs-lookup"><span data-stu-id="8ac20-121">Creating New Lync Phone Edition Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="8ac20-122">您可以使用 Windows PowerShell 和**CsUCPhoneConfiguration** Cmdlet，建立 Lync Phone Edition 設定設定（僅限在網站範圍內）。</span><span class="sxs-lookup"><span data-stu-id="8ac20-122">You can create Lync Phone Edition configuration settings can (at the site scope only) by using Windows PowerShell and the **New-CsUCPhoneConfiguration** cmdlet.</span></span> <span data-ttu-id="8ac20-123">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8ac20-123">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="8ac20-124">如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="8ac20-124">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-new-lync-phone-edition-configuration-settings-that-use-the-default-values"></a><span data-ttu-id="8ac20-125">若要建立使用預設值的新 Lync 手機版配置設定</span><span class="sxs-lookup"><span data-stu-id="8ac20-125">To create new Lync Phone Edition configuration settings that use the default values</span></span>

  - <span data-ttu-id="8ac20-126">這個命令會針對雷德蒙的網站建立一組新的 UC 手機設定：</span><span class="sxs-lookup"><span data-stu-id="8ac20-126">This command creates a new set of UC phone configuration settings for the Redmond site:</span></span>
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond"
    
    <span data-ttu-id="8ac20-127">因為在上述命令中沒有指定任何參數（強制身分識別參數以外），所以新的配置設定集合會將預設值用於其所有屬性。</span><span class="sxs-lookup"><span data-stu-id="8ac20-127">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties.</span></span>

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-new-lync-phone-edition-configuration-settings"></a><span data-ttu-id="8ac20-128">若要在建立新的 Lync Phone 版本設定時變更單一屬性值</span><span class="sxs-lookup"><span data-stu-id="8ac20-128">To change a single property value when creating new Lync Phone Edition configuration settings</span></span>

  - <span data-ttu-id="8ac20-129">若要建立使用不同屬性值的設定，只要包含適當的參數和參數值即可。</span><span class="sxs-lookup"><span data-stu-id="8ac20-129">To create settings that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="8ac20-130">例如，若要建立 UC 手機設定的集合，且根據預設，需要電話鎖定，請使用如下所示的命令：</span><span class="sxs-lookup"><span data-stu-id="8ac20-130">For example, to create a collection of UC phone configuration settings that, by default, require phone locking, use a command like this:</span></span>
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond" -EnforcePhoneLock $True

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-new-lync-phone-edition-configuration-settings"></a><span data-ttu-id="8ac20-131">若要在建立新的 Lync Phone Edition 設定時變更多個屬性值</span><span class="sxs-lookup"><span data-stu-id="8ac20-131">To change multiple property values when creating new Lync Phone Edition configuration settings</span></span>

  - <span data-ttu-id="8ac20-132">您可以透過包含多個參數來修改多個屬性值。</span><span class="sxs-lookup"><span data-stu-id="8ac20-132">Multiple property values can be modified by including multiple parameters.</span></span> <span data-ttu-id="8ac20-133">例如，這個命令會強制進行電話鎖定，也會將最小 PIN 長度設定為8位數：</span><span class="sxs-lookup"><span data-stu-id="8ac20-133">For example, this command enforces phone locking and also sets the minimum PIN length to 8 digits:</span></span>
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond" -EnforcePhoneLock $True -MinPhonePinLength 8

</div>

<span data-ttu-id="8ac20-134">如需詳細資訊，請參閱[新 CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg398445(v=OCS.15))。</span><span class="sxs-lookup"><span data-stu-id="8ac20-134">For details, see [New-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg398445(v=OCS.15)).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8ac20-135">請參閱</span><span class="sxs-lookup"><span data-stu-id="8ac20-135">See Also</span></span>


[<span data-ttu-id="8ac20-136">刪除 Lync Server 2013 中現有的 Lync Phone Edition 配置設定集合</span><span class="sxs-lookup"><span data-stu-id="8ac20-136">Delete an existing collection of Lync Phone Edition configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-lync-phone-edition-configuration-settings.md)  
[<span data-ttu-id="8ac20-137">在 Lync Server 2013 中設定 Lync Phone Edition 的安全性設定</span><span class="sxs-lookup"><span data-stu-id="8ac20-137">Configure security settings for Lync Phone Edition in Lync Server 2013</span></span>](lync-server-2013-configure-security-settings-for-lync-phone-edition.md)  
[<span data-ttu-id="8ac20-138">在 Lync Server 2013 中強制執行電話鎖定</span><span class="sxs-lookup"><span data-stu-id="8ac20-138">Enforce phone locking in Lync Server 2013</span></span>](lync-server-2013-enforce-phone-locking.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

