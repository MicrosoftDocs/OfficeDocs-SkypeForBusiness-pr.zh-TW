---
title: Lync Server 2013：啟用或停用 Iphone 的推播通知
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling or disabling push notifications for iPhones
ms:assetid: 8bbf531a-807f-4a8f-814a-94bfed8f97ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688122(v=OCS.15)
ms:contentKeyID: 49733719
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 28820bacf3208d8918e18e3bbb9904f762cfdd21
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207863"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enabling-or-disabling-push-notifications-for-iphones-in-lync-server-2013"></a><span data-ttu-id="f8bef-102">在 Lync Server 2013 中啟用或停用 Iphone 的推播通知</span><span class="sxs-lookup"><span data-stu-id="f8bef-102">Enabling or disabling push notifications for iPhones in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f8bef-103">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="f8bef-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="f8bef-104">即使行動應用程式不在使用中，也可以將「徽章」、圖示或警示等的推播通知傳送給 iPhone。</span><span class="sxs-lookup"><span data-stu-id="f8bef-104">Push notifications, in the form of badges, icons, or alerts, can be sent to an iPhone even when the mobile application is inactive.</span></span> <span data-ttu-id="f8bef-105">推播通知會通知使用者有新的或錯過的 IM 邀請和語音信箱等事件。</span><span class="sxs-lookup"><span data-stu-id="f8bef-105">Push notifications notify a user of events such as a new or missed IM invitation and voice mail.</span></span> <span data-ttu-id="f8bef-106">您可以使用 Lync Server 2013 控制台或 Lync Server 2013 管理命令介面，啟用或停用 iPhone 的推播通知。</span><span class="sxs-lookup"><span data-stu-id="f8bef-106">You can enable or disable push notifications for iPhone by using either Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-enable-push-notifications-for-iphone-by-using-lync-server-control-panel"></a><span data-ttu-id="f8bef-107">使用 Lync Server 控制台啟用 iPhone 的推播通知</span><span class="sxs-lookup"><span data-stu-id="f8bef-107">To enable push notifications for iPhone by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="f8bef-108">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="f8bef-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f8bef-109">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="f8bef-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f8bef-110">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="f8bef-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f8bef-111">在左導覽列中，按一下 [**用戶端**]，然後按一下 [**推播通知**設定] 瀏覽按鈕。</span><span class="sxs-lookup"><span data-stu-id="f8bef-111">In the left navigation bar, click **Clients**, and then click the **Push Notification Configuration** navigation button.</span></span>

4.  <span data-ttu-id="f8bef-112">在 [**推入通知**設定] 頁面上，按一下您要編輯的網站，然後按一下 [**編輯**] 功能表，再按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="f8bef-112">On the **Push Notification Configuration** page, click the site you want to edit, click the **Edit** menu, and then click **Show details**.</span></span>

5.  <span data-ttu-id="f8bef-113">按一下 [**啟用 Apple 推播通知**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="f8bef-113">Click the **Enable Apple push notifications** checkbox.</span></span>

6.  <span data-ttu-id="f8bef-114">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="f8bef-114">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-disable-push-notifications-for-iphone-by-using-lync-server-control-panel"></a><span data-ttu-id="f8bef-115">使用 Lync Server 控制台停用 iPhone 的推播通知</span><span class="sxs-lookup"><span data-stu-id="f8bef-115">To disable push notifications for iPhone by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="f8bef-116">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="f8bef-116">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f8bef-117">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="f8bef-117">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f8bef-118">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="f8bef-118">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f8bef-119">在左導覽列中，按一下 [**用戶端**]，然後按一下 [**推播通知**設定] 瀏覽按鈕。</span><span class="sxs-lookup"><span data-stu-id="f8bef-119">In the left navigation bar, click **Clients**, and then click the **Push Notification Configuration** navigation button.</span></span>

4.  <span data-ttu-id="f8bef-120">在 [**推入通知**設定] 頁面上，按一下您要編輯的網站，然後按一下 [**編輯**] 功能表，再按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="f8bef-120">On the **Push Notification Configuration** page, click the site you want to edit, click the **Edit** menu, and then click **Show details**.</span></span>

5.  <span data-ttu-id="f8bef-121">清除 [**啟用 Apple 推播通知**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="f8bef-121">Clear the **Enable Apple push notifications** checkbox.</span></span>

6.  <span data-ttu-id="f8bef-122">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="f8bef-122">Click **Commit**.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-push-notifications-to-iphone-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="f8bef-123">使用 Windows PowerShell Cmdlet 來啟用或停用向 iPhone 的推播通知</span><span class="sxs-lookup"><span data-stu-id="f8bef-123">Enabling or Disabling Push Notifications to iPhone by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="f8bef-124">您可以使用**Set-CsPushNotificationConfiguration** Cmdlet 來啟用或停用向 Apple iPhone 的推播通知。</span><span class="sxs-lookup"><span data-stu-id="f8bef-124">Push notifications to Apple iPhone can be enabled or disabled by using the **Set-CsPushNotificationConfiguration** cmdlet.</span></span> <span data-ttu-id="f8bef-125">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f8bef-125">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="f8bef-126">如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="f8bef-126">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-push-notifications-for-iphone"></a><span data-ttu-id="f8bef-127">啟用 iPhone 的推播通知</span><span class="sxs-lookup"><span data-stu-id="f8bef-127">To enable push notifications for iPhone</span></span>

  - <span data-ttu-id="f8bef-128">若要啟用 iPhone 的推播通知，請將 EnableApplePushNotificationService 屬性的值設為 True ($True) 。</span><span class="sxs-lookup"><span data-stu-id="f8bef-128">To enable push notifications for iPhone set the value of the EnableApplePushNotificationService property to True ($True).</span></span> <span data-ttu-id="f8bef-129">例如：</span><span class="sxs-lookup"><span data-stu-id="f8bef-129">For example:</span></span>
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableApplePushNotificationService $True

</div>

<div>

## <a name="to-disable-push-notifications-for-iphone"></a><span data-ttu-id="f8bef-130">停用 iPhone 的推播通知</span><span class="sxs-lookup"><span data-stu-id="f8bef-130">To disable push notifications for iPhone</span></span>

  - <span data-ttu-id="f8bef-131">若要停用針對 iPhone 的推播通知，請將 EnableApplePushNotificationService 屬性的值設為 False ($False) 。</span><span class="sxs-lookup"><span data-stu-id="f8bef-131">To disable push notifications for iPhone set the value of the EnableApplePushNotificationService property to False ($False).</span></span> <span data-ttu-id="f8bef-132">例如：</span><span class="sxs-lookup"><span data-stu-id="f8bef-132">For example:</span></span>
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableApplePushNotificationService $False

</div>

<span data-ttu-id="f8bef-133">如需詳細資訊，請參閱[Set-CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPushNotificationConfiguration) Cmdlet 的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="f8bef-133">For more information, see the help topic for the [Set-CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPushNotificationConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f8bef-134">另請參閱</span><span class="sxs-lookup"><span data-stu-id="f8bef-134">See Also</span></span>


[<span data-ttu-id="f8bef-135">在 Lync Server 2013 中設定推播通知</span><span class="sxs-lookup"><span data-stu-id="f8bef-135">Configuring for push notifications in Lync Server 2013</span></span>](lync-server-2013-configuring-for-push-notifications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

