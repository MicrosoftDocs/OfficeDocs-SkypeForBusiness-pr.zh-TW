---
title: Lync Server 2013：強制執行電話鎖定
description: Lync Server 2013：強制執行電話鎖定。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enforce phone locking
ms:assetid: 1f89298b-aea9-4952-93ca-0270b565792b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520963(v=OCS.15)
ms:contentKeyID: 48183594
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5afae4fa27edf9378bacc39a29697c9607b25c07
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575599"
---
# <a name="enforce-phone-locking-in-lync-server-2013"></a><span data-ttu-id="13014-103">在 Lync Server 2013 中強制執行電話鎖定</span><span class="sxs-lookup"><span data-stu-id="13014-103">Enforce phone locking in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="13014-104">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="13014-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="13014-105">出於安全性目的，可鎖定 Lync Phone Edition 裝置。</span><span class="sxs-lookup"><span data-stu-id="13014-105">Lync Phone Edition devices can be locked for security purposes.</span></span> <span data-ttu-id="13014-106">如果您強制執行電話鎖定，則執行 Lync Phone Edition 的裝置會在您設定的一段時間後鎖定。</span><span class="sxs-lookup"><span data-stu-id="13014-106">If you enforce phone lock, the device running Lync Phone Edition locks after a period of time that you configure.</span></span> <span data-ttu-id="13014-107">當電話鎖定時，使用者可以撥打電話，但無法存取行事曆和連絡人資訊、語音信箱或通話記錄或使用搜尋。</span><span class="sxs-lookup"><span data-stu-id="13014-107">When a phone is locked, a user can make calls but cannot access calendar and contact information, voice mail, or call logs or use search.</span></span> <span data-ttu-id="13014-108">若要解除電話鎖定，使用者會輸入 PIN 碼。</span><span class="sxs-lookup"><span data-stu-id="13014-108">To unlock the phone, the user enters a PIN.</span></span>

<span data-ttu-id="13014-109">若要強制執行電話鎖定，請使用 Lync Server 控制台或 Lync Server PowerShell Cmdlet 來啟用和設定。</span><span class="sxs-lookup"><span data-stu-id="13014-109">To enforce phone lock, enable and configure it by using Lync Server Control Panel or Lync Server PowerShell cmdlets.</span></span> <span data-ttu-id="13014-110">您可以以全域方式或僅在設定它的網站內強制執行電話鎖定。</span><span class="sxs-lookup"><span data-stu-id="13014-110">You can enforce phone lock globally or only within the site for which it is configured.</span></span>

<div>

## <a name="to-configure-and-enforce-the-phone-lock"></a><span data-ttu-id="13014-111">設定並強制執行電話鎖定</span><span class="sxs-lookup"><span data-stu-id="13014-111">To configure and enforce the phone lock</span></span>

1.  <span data-ttu-id="13014-112">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="13014-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="13014-113">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="13014-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="13014-114">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="13014-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="13014-115">依序按一下 **[用戶端]** 和 **[裝置設定]**。</span><span class="sxs-lookup"><span data-stu-id="13014-115">Click **Clients**, and then click **Device Configuration**.</span></span>

4.  <span data-ttu-id="13014-116">在 **[裝置設定]** 索引標籤的裝置設定清單中，按兩下您要變更電話鎖定設定的設定。</span><span class="sxs-lookup"><span data-stu-id="13014-116">On the **Device Configuration** tab, in the list of device configurations, double-click the configuration for which you want to change the phone lock settings.</span></span>

5.  <span data-ttu-id="13014-117">在 **[編輯裝置設定]** 對話方塊中，確認已選取 **[強制執行裝置鎖定]** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="13014-117">In the **Edit Device Configuration** dialog box, verify that the **Enforce device locking** check box is selected.</span></span>

6.  <span data-ttu-id="13014-118">在 [ **最小 PIN 碼長度**] 中，接受解除鎖定 PIN 必須包含或指定新值之位數下限的預設值。</span><span class="sxs-lookup"><span data-stu-id="13014-118">In **Minimum PIN length**, accept the default value for the minimum number of digits that the unlock PIN must contain or specify a new value.</span></span> <span data-ttu-id="13014-119">PIN 碼的長度範圍是四到15位數，預設值為6。</span><span class="sxs-lookup"><span data-stu-id="13014-119">The range for the PIN length is four to 15 digits, and the default is six.</span></span>

7.  <span data-ttu-id="13014-120">在 [ **電話鎖定**超時] 中，接受電話鎖定本身之前的最短時間長度的預設值，或指定新值。</span><span class="sxs-lookup"><span data-stu-id="13014-120">In **Phone lock time-out**, accept the default value for the minimum length of time before the phone locks itself or specify a new value.</span></span> <span data-ttu-id="13014-121">超時的範圍是0到60分鐘，預設值為10。</span><span class="sxs-lookup"><span data-stu-id="13014-121">The range for the timeout is 0 to 60 minutes, and the default is 10.</span></span> <span data-ttu-id="13014-122">輸入值，格式為 HH： MM： SS。</span><span class="sxs-lookup"><span data-stu-id="13014-122">Enter the value in the format HH:MM:SS.</span></span>

8.  <span data-ttu-id="13014-123">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="13014-123">Click **Commit**.</span></span>

</div>

<div>

## <a name="enforcing-phone-locking-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="13014-124">使用 Windows PowerShell Cmdlet 強制進行電話鎖定</span><span class="sxs-lookup"><span data-stu-id="13014-124">Enforcing Phone Locking by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="13014-125">您可以使用 Set-CsUCPhoneConfiguration Cmdlet 強制執行電話鎖定。</span><span class="sxs-lookup"><span data-stu-id="13014-125">Phone locking can be enforced by using the Set-CsUCPhoneConfiguration cmdlet.</span></span> <span data-ttu-id="13014-126">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="13014-126">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="13014-127">如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="13014-127">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-phone-locking"></a><span data-ttu-id="13014-128">啟用電話鎖定</span><span class="sxs-lookup"><span data-stu-id="13014-128">To enable phone locking</span></span>

  - <span data-ttu-id="13014-129">下列命令可啟用 Redmond 網站的電話鎖定。</span><span class="sxs-lookup"><span data-stu-id="13014-129">The following command enables phone locking for the Redmond site.</span></span> <span data-ttu-id="13014-130">若要停用電話鎖定，請將 EnforcePhoneLock 屬性設為 ($False)。</span><span class="sxs-lookup"><span data-stu-id="13014-130">To disable phone locking, set the EnforcePhoneLock property to False ($False).</span></span>
    
        Set-CsUCPhoneConfiguration -Identity" site:Redmond" -EnforcePhoneLock $True

</div>

<div>

## <a name="to-enable-phone-locking-and-modify-the-phone-lock-timeout"></a><span data-ttu-id="13014-131">啟用電話鎖定及修改電話鎖定超時</span><span class="sxs-lookup"><span data-stu-id="13014-131">To enable phone locking and modify the phone lock timeout</span></span>

  - <span data-ttu-id="13014-132">此命令可啟用電話鎖定，也可將電話鎖定逾時設為 30 分鐘。</span><span class="sxs-lookup"><span data-stu-id="13014-132">This command enables phone locking and also sets the phone lock timeout to 30 minutes.</span></span>
    
        Set-CsUCPhoneConfiguration -Identity" site:Redmond" -EnforcePhoneLock $True -PhoneLockTimeout "00:30:00"

</div>

<div>

## <a name="to-enable-phone-locking-throughout-the-organization"></a><span data-ttu-id="13014-133">在整個組織中啟用電話鎖定</span><span class="sxs-lookup"><span data-stu-id="13014-133">To enable phone locking throughout the organization</span></span>

  - <span data-ttu-id="13014-134">在此範例中，組織中所使用的所有 UC 電話組態設定都啟用了電話鎖定。</span><span class="sxs-lookup"><span data-stu-id="13014-134">In this example, phone locking is enabled on all the UC phone configuration settings in use in the organization.</span></span>
    
        Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration  -EnforcePhoneLock $True

</div>

<span data-ttu-id="13014-135">如需詳細資訊，請參閱 [Set-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsUCPhoneConfiguration) Cmdlet 的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="13014-135">For more information, see the help topic for the [Set-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsUCPhoneConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="13014-136">另請參閱</span><span class="sxs-lookup"><span data-stu-id="13014-136">See Also</span></span>


[<span data-ttu-id="13014-137">管理 Lync Server 2013 驗證</span><span class="sxs-lookup"><span data-stu-id="13014-137">Managing Lync Server 2013 authentication</span></span>](lync-server-2013-managing-lync-server-authentication.md)  


[<span data-ttu-id="13014-138">在 Lync Server 2013 中管理裝置、電話及用戶端應用程式</span><span class="sxs-lookup"><span data-stu-id="13014-138">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

