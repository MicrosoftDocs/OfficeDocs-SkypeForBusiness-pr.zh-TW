---
title: Lync Server 2013： 設定推入通知
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring for push notifications
ms:assetid: d77f2c06-0fe6-45d5-8f08-808ab871b3e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690047(v=OCS.15)
ms:contentKeyID: 48185574
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f92ae27b919df6a32f06921df97746680a68b030
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028954"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-for-push-notifications-in-lync-server-2013"></a><span data-ttu-id="0cb70-102">設定 Lync Server 2013 中的推入通知</span><span class="sxs-lookup"><span data-stu-id="0cb70-102">Configuring for push notifications in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0cb70-103">_**上次修改主題：** 2013年-02-12_</span><span class="sxs-lookup"><span data-stu-id="0cb70-103">_**Topic Last Modified:** 2013-02-12_</span></span>

<span data-ttu-id="0cb70-104">推入通知，形式的徽章、 圖示或提醒，可以傳送至行動裝置，只有非使用中的行動應用程式時，即使。</span><span class="sxs-lookup"><span data-stu-id="0cb70-104">Push notifications, in the form of badges, icons, or alerts, can be sent to a mobile device even when the mobile application is inactive.</span></span> <span data-ttu-id="0cb70-105">推入通知通知事件，例如新的或未接 IM 邀請與語音信箱的使用者。</span><span class="sxs-lookup"><span data-stu-id="0cb70-105">Push notifications notify a user of events such as a new or missed IM invitation and voice mail.</span></span> <span data-ttu-id="0cb70-106">Lync Server 2013 Mobility Service 將通知傳送至雲端式 Lync Server 推播通知服務，然後將通知傳送至 Apple 推播通知服務 (APNS) （適用於執行 Lync 2010 Mobile 用戶端 Apple 裝置） 其中或Microsoft 推播通知服務 (MPNS) （適用於執行 Lync 2010 Mobile 或 Lync 2013 行動用戶端的 Windows Phone 裝置）。</span><span class="sxs-lookup"><span data-stu-id="0cb70-106">The Lync Server 2013 Mobility Service sends the notifications to the cloud-based Lync Server Push Notification Service, which then sends the notifications to the Apple Push Notification Service (APNS) (for an Apple device running the Lync 2010 Mobile client) or the Microsoft Push Notification Service (MPNS) (for a Windows Phone device running the Lync 2010 Mobile or the Lync 2013 Mobile client).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="0cb70-107">如果您使用 Windows Phone 與 Lync 2010 Mobile 或 Lync 2013 行動用戶端，推播通知是很重要的考量。</span><span class="sxs-lookup"><span data-stu-id="0cb70-107">If you use Windows Phone with Lync 2010 Mobile or Lync 2013 Mobile client, push notification is an important consideration.</span></span><BR><span data-ttu-id="0cb70-108">如果您在 Apple 裝置上使用 Lync 2010 Mobile，推播通知是很重要的考量。</span><span class="sxs-lookup"><span data-stu-id="0cb70-108">If you use Lync 2010 Mobile on Apple devices, push notification is an important consideration.</span></span><BR><span data-ttu-id="0cb70-109">如果您在 Apple 裝置上使用 Lync 2013 行動，您不再需要推入通知。</span><span class="sxs-lookup"><span data-stu-id="0cb70-109">If you use Lync 2013 Mobile on Apple devices, you no longer need push notification.</span></span>



</div>

<span data-ttu-id="0cb70-110">設定您的拓撲支援推入通知，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="0cb70-110">Configure your topology to support push notifications by doing the following:</span></span>

  - <span data-ttu-id="0cb70-111">如果您的環境具有 Lync Server 2010 或 Lync Server 2013 Edge Server，您需要新增新主機服務提供者，Microsoft Lync Online，然後再設定裝載提供者同盟組織與 Lync Online 之間。</span><span class="sxs-lookup"><span data-stu-id="0cb70-111">If your environment has a Lync Server 2010 or Lync Server 2013 Edge Server, you need to add a new hosting provider, Microsoft Lync Online, and then set up hosting provider federation between your organization and Lync Online.</span></span>

  - <span data-ttu-id="0cb70-112">如果您的環境具有 Office Communications Server 2007 R2 Edge Server，您必須設定與 push.lync.com 的直接 SIP 同盟。</span><span class="sxs-lookup"><span data-stu-id="0cb70-112">If your environment has a Office Communications Server 2007 R2 Edge Server, you need to set up direct SIP federation with push.lync.com.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0cb70-113">Push.lync.com 是推入通知服務的 Microsoft Office 365 網域。</span><span class="sxs-lookup"><span data-stu-id="0cb70-113">Push.lync.com is a Microsoft Office 365 domain for Push Notification Service.</span></span>

    
    </div>

  - <span data-ttu-id="0cb70-114">若要啟用推播通知，您需要執行**Set-cspushnotificationconfiguration** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0cb70-114">To enable push notifications, you need to run the **Set-CsPushNotificationConfiguration** cmdlet.</span></span> <span data-ttu-id="0cb70-115">根據預設，推入通知被關閉的。</span><span class="sxs-lookup"><span data-stu-id="0cb70-115">By default, push notifications are turned off.</span></span>

  - <span data-ttu-id="0cb70-116">測試同盟設定和推入通知。</span><span class="sxs-lookup"><span data-stu-id="0cb70-116">Test the federation configuration and push notifications.</span></span>

<div>

## <a name="to-configure-for-push-notifications-with-lync-server-2013-or-lync-server-2010edge-server"></a><span data-ttu-id="0cb70-117">若要設定與 Lync Server 2013 或 Lync Server 2010 Edge Server 的推入通知</span><span class="sxs-lookup"><span data-stu-id="0cb70-117">To configure for push notifications with Lync Server 2013 or Lync Server 2010 Edge Server</span></span>

1.  <span data-ttu-id="0cb70-118">登入 Lync Server 管理命令介面和 Ocscore 的 RtcUniversalServerAdmins 群組成員身分安裝所在的電腦。</span><span class="sxs-lookup"><span data-stu-id="0cb70-118">Log on to a computer where Lync Server Management Shell and Ocscore are installed as a member of the RtcUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="0cb70-119">啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。</span><span class="sxs-lookup"><span data-stu-id="0cb70-119">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="0cb70-120">新增 Lync Server 線上裝載提供者。</span><span class="sxs-lookup"><span data-stu-id="0cb70-120">Add a Lync Server online hosting provider.</span></span> <span data-ttu-id="0cb70-121">在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="0cb70-121">At the command line, type:</span></span>
    
        New-CsHostingProvider -Identity <unique identifier for Lync Online hosting provider> -Enabled $True -ProxyFqdn <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
    
    <span data-ttu-id="0cb70-122">例如：</span><span class="sxs-lookup"><span data-stu-id="0cb70-122">For example:</span></span>
    
        New-CsHostingProvider -Identity "LyncOnline" -Enabled $True -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0cb70-123">您不能有一個以上的同盟關係與單一主機服務提供者。</span><span class="sxs-lookup"><span data-stu-id="0cb70-123">You cannot have more than one federation relationship with a single hosting provider.</span></span> <span data-ttu-id="0cb70-124">也就是說，如果您已經設定裝載提供者已與 sipfed.online.lync.com 的同盟關係，請勿加上另一個主機服務提供者，即使裝載提供者的身分識別是 Nm-lynconline-w15-long 以外的項目。</span><span class="sxs-lookup"><span data-stu-id="0cb70-124">That is, if you have already set up a hosting provider that has a federation relationship with sipfed.online.lync.com, do not add another hosting provider for it, even if the identity of the hosting provider is something other than LyncOnline.</span></span>

    
    </div>

4.  <span data-ttu-id="0cb70-125">設定裝載您的組織和推入通知服務在 Lync Online 之間的提供者同盟。</span><span class="sxs-lookup"><span data-stu-id="0cb70-125">Set up hosting provider federation between your organization and the Push Notification Service at Lync Online.</span></span> <span data-ttu-id="0cb70-126">在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="0cb70-126">At the command line, type:</span></span>
    
        New-CsAllowedDomain -Identity "push.lync.com"

</div>

<div>

## <a name="to-configure-for-push-notifications-with-office-communications-server-2007-r2edge-server"></a><span data-ttu-id="0cb70-127">若要設定與 Office Communications Server 2007 R2 Edge Server 的推入通知</span><span class="sxs-lookup"><span data-stu-id="0cb70-127">To configure for push notifications with Office Communications Server 2007 R2 Edge Server</span></span>

1.  <span data-ttu-id="0cb70-128">使用 RtcUniversalServerAdmins 群組成員身分登入 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="0cb70-128">Log on to the Edge Server as a member of the RtcUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="0cb70-129">按一下 [**開始]**[**所有程式]**、 [**系統管理工具**]，然後按一下 [**電腦管理]**。</span><span class="sxs-lookup"><span data-stu-id="0cb70-129">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **Computer Management**.</span></span>

3.  <span data-ttu-id="0cb70-130">在主控台樹狀目錄中，展開 [**服務及應用程式**，以滑鼠右鍵按一下 [ **Microsoft Office Communications Server 2007 R2**，，然後按一下**屬性**。</span><span class="sxs-lookup"><span data-stu-id="0cb70-130">In the console tree, expand **Services and Applications**, right-click **Microsoft Office Communications Server 2007 R2**, and then click **Properties**.</span></span>

4.  <span data-ttu-id="0cb70-131">[**允許**] 索引標籤中，按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="0cb70-131">On the **Allow** tab, click **Add**.</span></span>

5.  <span data-ttu-id="0cb70-132">在 [**新增同盟協力廠商**] 對話方塊中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="0cb70-132">In the **Add Federated Partner** dialog box, do the following:</span></span>
    
      - <span data-ttu-id="0cb70-133">在 [**同盟協力廠商網域名稱**] 中，輸入**push.lync.com**。</span><span class="sxs-lookup"><span data-stu-id="0cb70-133">In **Federated partner domain name**, type **push.lync.com**.</span></span>
    
      - <span data-ttu-id="0cb70-134">在 [**同盟協力廠商 Access Edge Server**，輸入**sipfed.online.lync.com**。</span><span class="sxs-lookup"><span data-stu-id="0cb70-134">In **Federated partner Access Edge Server**, type **sipfed.online.lync.com**.</span></span>
    
      - <span data-ttu-id="0cb70-135">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0cb70-135">Click **OK**.</span></span>

</div>

<div>

## <a name="to-enable-push-notifications"></a><span data-ttu-id="0cb70-136">若要啟用推入通知</span><span class="sxs-lookup"><span data-stu-id="0cb70-136">To enable push notifications</span></span>

1.  <span data-ttu-id="0cb70-137">登入 Lync Server 管理命令介面和 Ocscore CsAdministrator 角色的成員身分安裝所在的電腦。</span><span class="sxs-lookup"><span data-stu-id="0cb70-137">Log on to a computer where Lync Server Management Shell and Ocscore are installed as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="0cb70-138">啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。</span><span class="sxs-lookup"><span data-stu-id="0cb70-138">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="0cb70-139">啟用推入通知。</span><span class="sxs-lookup"><span data-stu-id="0cb70-139">Enable push notifications.</span></span> <span data-ttu-id="0cb70-140">在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="0cb70-140">At the command line, type:</span></span>
    
        Set-CsPushNotificationConfiguration -EnableApplePushNotificationService $True -EnableMicrosoftPushNotificationService $True

4.  <span data-ttu-id="0cb70-141">啟用同盟。</span><span class="sxs-lookup"><span data-stu-id="0cb70-141">Enable federation.</span></span> <span data-ttu-id="0cb70-142">在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="0cb70-142">At the command line, type:</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

</div>

<div>

## <a name="to-test-federation-and-push-notifications"></a><span data-ttu-id="0cb70-143">測試同盟和推入通知</span><span class="sxs-lookup"><span data-stu-id="0cb70-143">To test federation and push notifications</span></span>

1.  <span data-ttu-id="0cb70-144">登入 Lync Server 管理命令介面和 Ocscore CsAdministrator 角色的成員身分安裝所在的電腦。</span><span class="sxs-lookup"><span data-stu-id="0cb70-144">Log on to a computer where Lync Server Management Shell and Ocscore are installed as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="0cb70-145">啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。</span><span class="sxs-lookup"><span data-stu-id="0cb70-145">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="0cb70-146">測試同盟設定。</span><span class="sxs-lookup"><span data-stu-id="0cb70-146">Test the federation configuration.</span></span> <span data-ttu-id="0cb70-147">在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="0cb70-147">At the command line, type:</span></span>
    
        Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
    
    <span data-ttu-id="0cb70-148">例如：</span><span class="sxs-lookup"><span data-stu-id="0cb70-148">For example:</span></span>
    
        Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com

4.  <span data-ttu-id="0cb70-149">測試推入通知。</span><span class="sxs-lookup"><span data-stu-id="0cb70-149">Test push notifications.</span></span> <span data-ttu-id="0cb70-150">在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="0cb70-150">At the command line, type:</span></span>
    
        Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
    
    <span data-ttu-id="0cb70-151">例如：</span><span class="sxs-lookup"><span data-stu-id="0cb70-151">For example:</span></span>
    
        Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0cb70-152">請參閱</span><span class="sxs-lookup"><span data-stu-id="0cb70-152">See Also</span></span>


[<span data-ttu-id="0cb70-153">Test-csfederatedpartner</span><span class="sxs-lookup"><span data-stu-id="0cb70-153">Test-CsFederatedPartner</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner)  
[<span data-ttu-id="0cb70-154">Test-csmcxpushnotification</span><span class="sxs-lookup"><span data-stu-id="0cb70-154">Test-CsMcxPushNotification</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxPushNotification)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

