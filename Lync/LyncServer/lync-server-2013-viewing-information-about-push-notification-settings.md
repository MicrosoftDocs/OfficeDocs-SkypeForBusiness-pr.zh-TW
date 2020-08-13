---
title: Lync Server 2013：查看推播通知設定的資訊
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing information about push notification settings
ms:assetid: be5c6b01-4294-4d17-9772-fed40201e8a5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721868(v=OCS.15)
ms:contentKeyID: 49733801
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 075deabdbc57bd809fce4bf3e4635309f367d69c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211239"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="viewing-information-about-push-notification-settings-in-lync-server-2013"></a><span data-ttu-id="9b138-102">在 Lync Server 2013 中查看推播通知設定的相關資訊</span><span class="sxs-lookup"><span data-stu-id="9b138-102">Viewing information about push notification settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9b138-103">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="9b138-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="9b138-104">即使當行動應用程式非使用中時，也可以將「徽章」、圖示或警示等推播通知傳送給行動裝置。</span><span class="sxs-lookup"><span data-stu-id="9b138-104">Push notifications, in the form of badges, icons, or alerts, can be sent to a mobile device even when the mobile application is inactive.</span></span> <span data-ttu-id="9b138-105">推播通知會通知使用者有新的或錯過的 IM 邀請和語音信箱等事件。</span><span class="sxs-lookup"><span data-stu-id="9b138-105">Push notifications notify a user of events such as a new or missed IM invitation and voice mail.</span></span> <span data-ttu-id="9b138-106">您可以使用 Lync Server 2013 控制台或 Lync Server 2013 管理命令介面，查看行動裝置的資訊推播通知設定。</span><span class="sxs-lookup"><span data-stu-id="9b138-106">You can view information push notifications settings for mobile devices by using either Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-view-push-notification-information-from-lync-server-control-panel"></a><span data-ttu-id="9b138-107">從 Lync Server 控制台查看推播通知資訊</span><span class="sxs-lookup"><span data-stu-id="9b138-107">To view push notification information from Lync Server Control Panel</span></span>

1.  <span data-ttu-id="9b138-108">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="9b138-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9b138-109">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="9b138-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="9b138-110">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="9b138-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="9b138-111">在左導覽列中，按一下 [**用戶端**]，然後按一下 [**推播通知**設定] 瀏覽按鈕。</span><span class="sxs-lookup"><span data-stu-id="9b138-111">In the left navigation bar, click **Clients**, and then click the **Push Notification Configuration** navigation button.</span></span>

4.  <span data-ttu-id="9b138-112">在 [**推入通知**設定] 頁面上，按一下您要查看的網站，然後按一下 [**編輯**] 功能表，再按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="9b138-112">On the **Push Notification Configuration** page, click the site you want to view, click the **Edit** menu, and then click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-push-notification-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="9b138-113">使用 Windows PowerShell Cmdlet 來查看推播通知資訊</span><span class="sxs-lookup"><span data-stu-id="9b138-113">Viewing Push Notification Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="9b138-114">您可以使用 Windows PowerShell 和**Get-CsPushNotificationConfiguration** Cmdlet 來查看推播通知設定設定。</span><span class="sxs-lookup"><span data-stu-id="9b138-114">You can view push notification configuration settings by using Windows PowerShell and the **Get-CsPushNotificationConfiguration** cmdlet.</span></span> <span data-ttu-id="9b138-115">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9b138-115">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="9b138-116">如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="9b138-116">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-push-notification-configuration-information"></a><span data-ttu-id="9b138-117">若要查看推播通知設定資訊</span><span class="sxs-lookup"><span data-stu-id="9b138-117">To view push notification configuration information</span></span>

  - <span data-ttu-id="9b138-118">若要查看所有推播通知設定設定的資訊，請在 Lync Server 管理命令介面中輸入下列命令，然後按 ENTER 鍵：</span><span class="sxs-lookup"><span data-stu-id="9b138-118">To view information about all your push notification configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsPushNotificationConfiguration
    
    <span data-ttu-id="9b138-119">如此將傳回類似如下的資訊：</span><span class="sxs-lookup"><span data-stu-id="9b138-119">That will return information similar to this:</span></span>
    
        Identity                               : Global
        EnableApplePushNotificationService     : False
        EnableMicrosoftPushNotificationService : False

</div>

<span data-ttu-id="9b138-120">如需詳細資訊，請參閱[Get-CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsPushNotificationConfiguration) Cmdlet 的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="9b138-120">For more information, see the help topic for the [Get-CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsPushNotificationConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9b138-121">另請參閱</span><span class="sxs-lookup"><span data-stu-id="9b138-121">See Also</span></span>


[<span data-ttu-id="9b138-122">在 Lync Server 2013 中設定推播通知</span><span class="sxs-lookup"><span data-stu-id="9b138-122">Configuring for push notifications in Lync Server 2013</span></span>](lync-server-2013-configuring-for-push-notifications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

