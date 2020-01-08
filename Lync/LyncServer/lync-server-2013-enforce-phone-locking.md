---
title: Lync Server 2013：強制執行電話鎖定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enforce phone locking
ms:assetid: 1f89298b-aea9-4952-93ca-0270b565792b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520963(v=OCS.15)
ms:contentKeyID: 48183594
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4961aabf2edce33f1e5975497844704ac0feae03
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982670"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enforce-phone-locking-in-lync-server-2013"></a><span data-ttu-id="d5072-102">在 Lync Server 2013 中強制執行電話鎖定</span><span class="sxs-lookup"><span data-stu-id="d5072-102">Enforce phone locking in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d5072-103">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="d5072-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="d5072-104">出於安全性考慮，您可以鎖定 Lync 手機版裝置。</span><span class="sxs-lookup"><span data-stu-id="d5072-104">Lync Phone Edition devices can be locked for security purposes.</span></span> <span data-ttu-id="d5072-105">如果您強制執行電話鎖定，則在您設定的一段時間後，執行 Lync Phone Edition 的裝置會封鎖。</span><span class="sxs-lookup"><span data-stu-id="d5072-105">If you enforce phone lock, the device running Lync Phone Edition locks after a period of time that you configure.</span></span> <span data-ttu-id="d5072-106">當手機鎖定時，使用者可以撥打電話，但無法存取行事曆和連絡人資訊、語音信箱或通話記錄，或使用搜尋。</span><span class="sxs-lookup"><span data-stu-id="d5072-106">When a phone is locked, a user can make calls but cannot access calendar and contact information, voice mail, or call logs or use search.</span></span> <span data-ttu-id="d5072-107">若要解除鎖定電話，使用者可以輸入 PIN。</span><span class="sxs-lookup"><span data-stu-id="d5072-107">To unlock the phone, the user enters a PIN.</span></span>

<span data-ttu-id="d5072-108">若要強制執行電話鎖定，請使用 Lync Server 的 [控制台] 或 [Lync Server PowerShell Cmdlet] 來啟用和設定。</span><span class="sxs-lookup"><span data-stu-id="d5072-108">To enforce phone lock, enable and configure it by using Lync Server Control Panel or Lync Server PowerShell cmdlets.</span></span> <span data-ttu-id="d5072-109">您可以全域或只在其設定的網站中強制執行電話鎖定。</span><span class="sxs-lookup"><span data-stu-id="d5072-109">You can enforce phone lock globally or only within the site for which it is configured.</span></span>

<div>

## <a name="to-configure-and-enforce-the-phone-lock"></a><span data-ttu-id="d5072-110">設定和強制執行電話鎖</span><span class="sxs-lookup"><span data-stu-id="d5072-110">To configure and enforce the phone lock</span></span>

1.  <span data-ttu-id="d5072-111">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="d5072-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d5072-112">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="d5072-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d5072-113">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="d5072-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d5072-114">按一下 [**用戶端**]，然後按一下 [**裝置配置**]。</span><span class="sxs-lookup"><span data-stu-id="d5072-114">Click **Clients**, and then click **Device Configuration**.</span></span>

4.  <span data-ttu-id="d5072-115">在 [**裝置**設定] 索引標籤上，于裝置配置清單中，按兩下您要變更電話鎖定設定的配置。</span><span class="sxs-lookup"><span data-stu-id="d5072-115">On the **Device Configuration** tab, in the list of device configurations, double-click the configuration for which you want to change the phone lock settings.</span></span>

5.  <span data-ttu-id="d5072-116">在 [**編輯裝置**設定] 對話方塊中，確認已選取 [**強制裝置鎖定**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="d5072-116">In the **Edit Device Configuration** dialog box, verify that the **Enforce device locking** check box is selected.</span></span>

6.  <span data-ttu-id="d5072-117">在 [**最小 PIN 長度**] 中，接受解除鎖定 PIN 必須包含或指定新值的最小位數數的預設值。</span><span class="sxs-lookup"><span data-stu-id="d5072-117">In **Minimum PIN length**, accept the default value for the minimum number of digits that the unlock PIN must contain or specify a new value.</span></span> <span data-ttu-id="d5072-118">PIN 長度的範圍是4到15個數字，預設值是6。</span><span class="sxs-lookup"><span data-stu-id="d5072-118">The range for the PIN length is four to 15 digits, and the default is six.</span></span>

7.  <span data-ttu-id="d5072-119">在 [**電話封鎖**超時] 中，接受手機鎖定本身或指定新值前的最短時間長度的預設值。</span><span class="sxs-lookup"><span data-stu-id="d5072-119">In **Phone lock time-out**, accept the default value for the minimum length of time before the phone locks itself or specify a new value.</span></span> <span data-ttu-id="d5072-120">超時的範圍是0到60分鐘，而預設值為10。</span><span class="sxs-lookup"><span data-stu-id="d5072-120">The range for the timeout is 0 to 60 minutes, and the default is 10.</span></span> <span data-ttu-id="d5072-121">以 HH： MM： SS 格式輸入值。</span><span class="sxs-lookup"><span data-stu-id="d5072-121">Enter the value in the format HH:MM:SS.</span></span>

8.  <span data-ttu-id="d5072-122">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d5072-122">Click **Commit**.</span></span>

</div>

<div>

## <a name="enforcing-phone-locking-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="d5072-123">使用 Windows PowerShell Cmdlet 強制進行電話鎖定</span><span class="sxs-lookup"><span data-stu-id="d5072-123">Enforcing Phone Locking by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="d5072-124">您可以使用 CsUCPhoneConfiguration Cmdlet 來強制執行電話鎖定。</span><span class="sxs-lookup"><span data-stu-id="d5072-124">Phone locking can be enforced by using the Set-CsUCPhoneConfiguration cmdlet.</span></span> <span data-ttu-id="d5072-125">這個 Cmdlet 可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行。</span><span class="sxs-lookup"><span data-stu-id="d5072-125">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="d5072-126">如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="d5072-126">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-phone-locking"></a><span data-ttu-id="d5072-127">啟用電話鎖定</span><span class="sxs-lookup"><span data-stu-id="d5072-127">To enable phone locking</span></span>

  - <span data-ttu-id="d5072-128">下列命令可讓雷德蒙網站的電話封鎖。</span><span class="sxs-lookup"><span data-stu-id="d5072-128">The following command enables phone locking for the Redmond site.</span></span> <span data-ttu-id="d5072-129">若要停用電話鎖定，請將 EnforcePhoneLock 屬性設定為 False （$False）。</span><span class="sxs-lookup"><span data-stu-id="d5072-129">To disable phone locking, set the EnforcePhoneLock property to False ($False).</span></span>
    
        Set-CsUCPhoneConfiguration -Identity" site:Redmond" -EnforcePhoneLock $True

</div>

<div>

## <a name="to-enable-phone-locking-and-modify-the-phone-lock-timeout"></a><span data-ttu-id="d5072-130">啟用電話封鎖及修改電話封鎖超時</span><span class="sxs-lookup"><span data-stu-id="d5072-130">To enable phone locking and modify the phone lock timeout</span></span>

  - <span data-ttu-id="d5072-131">這個命令會啟用電話鎖定，同時也會將電話封鎖超時設定為30分鐘。</span><span class="sxs-lookup"><span data-stu-id="d5072-131">This command enables phone locking and also sets the phone lock timeout to 30 minutes.</span></span>
    
        Set-CsUCPhoneConfiguration -Identity" site:Redmond" -EnforcePhoneLock $True -PhoneLockTimeout "00:30:00"

</div>

<div>

## <a name="to-enable-phone-locking-throughout-the-organization"></a><span data-ttu-id="d5072-132">若要在整個組織中啟用電話鎖定</span><span class="sxs-lookup"><span data-stu-id="d5072-132">To enable phone locking throughout the organization</span></span>

  - <span data-ttu-id="d5072-133">在這個範例中，在組織中使用的所有 UC 手機設定設定都已啟用電話鎖定。</span><span class="sxs-lookup"><span data-stu-id="d5072-133">In this example, phone locking is enabled on all the UC phone configuration settings in use in the organization.</span></span>
    
        Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration  -EnforcePhoneLock $True

</div>

<span data-ttu-id="d5072-134">如需詳細資訊，請參閱[CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsUCPhoneConfiguration) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="d5072-134">For more information, see the help topic for the [Set-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsUCPhoneConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d5072-135">請參閱</span><span class="sxs-lookup"><span data-stu-id="d5072-135">See Also</span></span>


[<span data-ttu-id="d5072-136">管理 Lync Server 2013 驗證</span><span class="sxs-lookup"><span data-stu-id="d5072-136">Managing Lync Server 2013 authentication</span></span>](lync-server-2013-managing-lync-server-authentication.md)  


[<span data-ttu-id="d5072-137">在 Lync Server 2013 中管理裝置、電話及用戶端應用程式</span><span class="sxs-lookup"><span data-stu-id="d5072-137">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

