---
title: Lync Server 2013：設定 Lync Phone Edition 的安全性設定
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
ms.openlocfilehash: 6f414eb395025b359d074bb1d5882b20919eb3f8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730013"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-security-settings-for-lync-phone-edition-in-lync-server-2013"></a><span data-ttu-id="c7125-102">在 Lync Server 2013 中設定 Lync Phone Edition 的安全性設定</span><span class="sxs-lookup"><span data-stu-id="c7125-102">Configure security settings for Lync Phone Edition in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c7125-103">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="c7125-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="c7125-104">透過您的 SIP 安全性設定和電話鎖定設定，協助改善執行 Lync 手機版本之裝置的安全性。</span><span class="sxs-lookup"><span data-stu-id="c7125-104">Help improve the security of devices running Lync Phone Edition via your SIP security setting and phone lock settings.</span></span>

<div>

## <a name="to-configure-security-settings-for-lync-phone-edition"></a><span data-ttu-id="c7125-105">若要設定 Lync Phone Edition 的安全性設定</span><span class="sxs-lookup"><span data-stu-id="c7125-105">To configure security settings for Lync Phone Edition</span></span>

1.  <span data-ttu-id="c7125-106">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="c7125-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c7125-107">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="c7125-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c7125-108">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="c7125-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c7125-109">在左側導覽列中，按一下 [**用戶端**]，然後按一下 [**裝置**設定]。</span><span class="sxs-lookup"><span data-stu-id="c7125-109">In the left navigation bar, click **Clients**, and then click **Device Configuration**.</span></span>

4.  <span data-ttu-id="c7125-110">在 [**裝置**設定] 頁面上，于裝置配置清單中，按兩下您要變更其安全性設定的配置。</span><span class="sxs-lookup"><span data-stu-id="c7125-110">On the **Device Configuration** page, in the list of device configurations, double-click the configuration for which you want to change security settings.</span></span>

5.  <span data-ttu-id="c7125-111">在 [**編輯裝置**設定] 的 [ **sip 安全性**] 中，指定 sip 安全等級。</span><span class="sxs-lookup"><span data-stu-id="c7125-111">In **Edit Device Configuration**, in **SIP security**, specify the SIP security level.</span></span> <span data-ttu-id="c7125-112">預設層級為 [**高**]，我們建議使用它。</span><span class="sxs-lookup"><span data-stu-id="c7125-112">The default level is **High**, which we recommend using.</span></span>

6.  <span data-ttu-id="c7125-113">在 [**編輯裝置**設定] 的 [**電話封鎖**] 底下，選取或清除 [**強制裝置鎖定**] 核取方塊（預設為選取），並指定最小 PIN 長度（預設為6個字元）和超時期間（預設為10分鐘）。</span><span class="sxs-lookup"><span data-stu-id="c7125-113">In **Edit Device Configuration**, under **Phone Lock**, select or clear the **Enforce device locking** check box (selected by default) and specify the minimum PIN length (6 characters by default) and timeout period (10 minutes by default).</span></span> <span data-ttu-id="c7125-114">我們建議您使用這些預設值，或增加 PIN 長度及/或減少超時時間。</span><span class="sxs-lookup"><span data-stu-id="c7125-114">We recommend using these defaults or increasing the PIN length and/or decreasing the timeout period.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c7125-115">如需詳細資訊，請參閱<A href="lync-server-2013-enforce-phone-locking.md">在 Lync Server 2013 中強制執行電話封鎖</A>。</span><span class="sxs-lookup"><span data-stu-id="c7125-115">For details, see <A href="lync-server-2013-enforce-phone-locking.md">Enforce phone locking in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="configuring-security-settings-for-lync-phone-edition-phones-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="c7125-116">使用 Windows PowerShell Cmdlet 設定 Lync Phone Edition 手機的安全性設定</span><span class="sxs-lookup"><span data-stu-id="c7125-116">Configuring Security Settings for Lync Phone Edition Phones by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="c7125-117">您可以使用 Lync Server 管理命令介面和**CsUCPhoneConfiguration** Cmdlet 來管理安全性設定。</span><span class="sxs-lookup"><span data-stu-id="c7125-117">Security settings can be managed by using Lync Server Management Shell and the **Get-CsUCPhoneConfiguration** cmdlet.</span></span> <span data-ttu-id="c7125-118">這個 Cmdlet 可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行。</span><span class="sxs-lookup"><span data-stu-id="c7125-118">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="c7125-119">如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="c7125-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-modify-the-sip-security-mode"></a><span data-ttu-id="c7125-120">修改 SIP 安全模式</span><span class="sxs-lookup"><span data-stu-id="c7125-120">To modify the SIP security mode</span></span>

  - <span data-ttu-id="c7125-121">這個命令會將 UC 手機設定的全域集合的 SIPSecurityMode 設定為 [中]。</span><span class="sxs-lookup"><span data-stu-id="c7125-121">This command sets the SIPSecurityMode for the global collection of UC phone settings to Medium.</span></span> <span data-ttu-id="c7125-122">SIP 安全性也可以設定為 [低] 或 [高] （預設值）。</span><span class="sxs-lookup"><span data-stu-id="c7125-122">SIP security could also be set to Low or High (the default value).</span></span>
    
        Set-CsUCPhoneConfiguration -Identity global -SIPSecurityMode "Medium"

</div>

<div>

## <a name="to-modify-the-minimum-pin-length"></a><span data-ttu-id="c7125-123">若要修改最小 PIN 長度</span><span class="sxs-lookup"><span data-stu-id="c7125-123">To modify the minimum PIN length</span></span>

  - <span data-ttu-id="c7125-124">在這個範例中，所有的 UC 電話設定都經過修改，以要求最小 PIN 長度為7位數。</span><span class="sxs-lookup"><span data-stu-id="c7125-124">In this example, all the UC phone settings are modified to require a minimum PIN length of 7 digits.</span></span>
    
        Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration -MinPhonePinLength 7

</div>

<span data-ttu-id="c7125-125">如需詳細資訊，請參閱[CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration)。</span><span class="sxs-lookup"><span data-stu-id="c7125-125">For details, see [Get-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c7125-126">請參閱</span><span class="sxs-lookup"><span data-stu-id="c7125-126">See Also</span></span>


[<span data-ttu-id="c7125-127">管理 Lync Server 2013 驗證</span><span class="sxs-lookup"><span data-stu-id="c7125-127">Managing Lync Server 2013 authentication</span></span>](lync-server-2013-managing-lync-server-authentication.md)  


[<span data-ttu-id="c7125-128">在 Lync Server 2013 中管理裝置、電話及用戶端應用程式</span><span class="sxs-lookup"><span data-stu-id="c7125-128">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

