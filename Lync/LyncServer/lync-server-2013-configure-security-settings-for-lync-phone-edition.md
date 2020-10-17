---
title: Lync Server 2013：設定 Lync Phone Edition 的安全性設定
description: Lync Server 2013：設定 Lync Phone Edition 的安全性設定。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure security settings for Lync Phone Edition
ms:assetid: 6e7cec17-8a79-4428-9300-8821256c46cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521014(v=OCS.15)
ms:contentKeyID: 48184464
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82e6a6488db66a8497930ee6b2d1aec6fc8b0b2d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564349"
---
# <a name="configure-security-settings-for-lync-phone-edition-in-lync-server-2013"></a><span data-ttu-id="501da-103">在 Lync Server 2013 中設定 Lync Phone Edition 的安全性設定</span><span class="sxs-lookup"><span data-stu-id="501da-103">Configure security settings for Lync Phone Edition in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="501da-104">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="501da-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="501da-105">透過您的 SIP 安全性設定和電話鎖定設定，協助改善執行 Lync Phone Edition 之裝置的安全性。</span><span class="sxs-lookup"><span data-stu-id="501da-105">Help improve the security of devices running Lync Phone Edition via your SIP security setting and phone lock settings.</span></span>

<div>

## <a name="to-configure-security-settings-for-lync-phone-edition"></a><span data-ttu-id="501da-106">設定 Lync Phone Edition 的安全性設定</span><span class="sxs-lookup"><span data-stu-id="501da-106">To configure security settings for Lync Phone Edition</span></span>

1.  <span data-ttu-id="501da-107">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="501da-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="501da-108">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="501da-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="501da-109">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="501da-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="501da-110">在左導覽列中，依序按一下 **[用戶端]** 和 **[裝置設定]**。</span><span class="sxs-lookup"><span data-stu-id="501da-110">In the left navigation bar, click **Clients**, and then click **Device Configuration**.</span></span>

4.  <span data-ttu-id="501da-111">在 **[裝置設定]** 頁面的裝置設定清單中，按兩下想要變更其安全性設定的設定。</span><span class="sxs-lookup"><span data-stu-id="501da-111">On the **Device Configuration** page, in the list of device configurations, double-click the configuration for which you want to change security settings.</span></span>

5.  <span data-ttu-id="501da-p102">在 **[編輯裝置設定]** 的 **[SIP 安全性]** 中指定 SIP 安全性等級。建議您使用 **[高]** 預設等級。</span><span class="sxs-lookup"><span data-stu-id="501da-p102">In **Edit Device Configuration**, in **SIP security**, specify the SIP security level. The default level is **High**, which we recommend using.</span></span>

6.  <span data-ttu-id="501da-p103">在 **[編輯裝置設定]** 的 **[電話鎖定]** 下方，請選取或清除 **[強制執行裝置鎖定]** 核取方塊 (預設選取)，並指定最小 PIN 長度限制 (預設為 6 個字元) 和逾時期限 (預設為 10 分鐘)。建議您使用這些預設值或增加 PIN 長度及/或縮短逾時期限。</span><span class="sxs-lookup"><span data-stu-id="501da-p103">In **Edit Device Configuration**, under **Phone Lock**, select or clear the **Enforce device locking** check box (selected by default) and specify the minimum PIN length (6 characters by default) and timeout period (10 minutes by default). We recommend using these defaults or increasing the PIN length and/or decreasing the timeout period.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="501da-116">如需詳細資訊，請參閱 <A href="lync-server-2013-enforce-phone-locking.md">在 Lync Server 2013 中強制進行電話鎖定</A>。</span><span class="sxs-lookup"><span data-stu-id="501da-116">For details, see <A href="lync-server-2013-enforce-phone-locking.md">Enforce phone locking in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="configuring-security-settings-for-lync-phone-edition-phones-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="501da-117">使用 Windows PowerShell Cmdlet 設定 Lync Phone Edition 電話的安全性設定</span><span class="sxs-lookup"><span data-stu-id="501da-117">Configuring Security Settings for Lync Phone Edition Phones by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="501da-118">您可以使用 Lync Server 管理命令介面和 **Get-CsUCPhoneConfiguration** Cmdlet 來管理安全性設定。</span><span class="sxs-lookup"><span data-stu-id="501da-118">Security settings can be managed by using Lync Server Management Shell and the **Get-CsUCPhoneConfiguration** cmdlet.</span></span> <span data-ttu-id="501da-119">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="501da-119">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="501da-120">如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="501da-120">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-modify-the-sip-security-mode"></a><span data-ttu-id="501da-121">修改 SIP 安全性模式</span><span class="sxs-lookup"><span data-stu-id="501da-121">To modify the SIP security mode</span></span>

  - <span data-ttu-id="501da-p105">這個命令會將 UC 電話設定全域集合的 SIPSecurityMode 設為 Medium，亦會將 SIP 安全性設為 Low 或 High (預設值)。</span><span class="sxs-lookup"><span data-stu-id="501da-p105">This command sets the SIPSecurityMode for the global collection of UC phone settings to Medium. SIP security could also be set to Low or High (the default value).</span></span>
    
        Set-CsUCPhoneConfiguration -Identity global -SIPSecurityMode "Medium"

</div>

<div>

## <a name="to-modify-the-minimum-pin-length"></a><span data-ttu-id="501da-124">修改最小 PIN 長度</span><span class="sxs-lookup"><span data-stu-id="501da-124">To modify the minimum PIN length</span></span>

  - <span data-ttu-id="501da-125">在此範例中，所有 UC 電話設定皆將最小 PIN 長度限制修改為 7 位數。</span><span class="sxs-lookup"><span data-stu-id="501da-125">In this example, all the UC phone settings are modified to require a minimum PIN length of 7 digits.</span></span>
    
        Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration -MinPhonePinLength 7

</div>

<span data-ttu-id="501da-126">如需詳細資訊，請參閱 [Get-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration)。</span><span class="sxs-lookup"><span data-stu-id="501da-126">For details, see [Get-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="501da-127">另請參閱</span><span class="sxs-lookup"><span data-stu-id="501da-127">See Also</span></span>


[<span data-ttu-id="501da-128">管理 Lync Server 2013 驗證</span><span class="sxs-lookup"><span data-stu-id="501da-128">Managing Lync Server 2013 authentication</span></span>](lync-server-2013-managing-lync-server-authentication.md)  


[<span data-ttu-id="501da-129">在 Lync Server 2013 中管理裝置、電話及用戶端應用程式</span><span class="sxs-lookup"><span data-stu-id="501da-129">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

