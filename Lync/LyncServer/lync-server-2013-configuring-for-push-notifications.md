---
title: Lync Server 2013：設定推播通知
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
ms.openlocfilehash: c34b49d6c968effa46005a01df286d14fcff394c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728983"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-for-push-notifications-in-lync-server-2013"></a><span data-ttu-id="af5ef-102">在 Lync Server 2013 中設定推播通知</span><span class="sxs-lookup"><span data-stu-id="af5ef-102">Configuring for push notifications in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="af5ef-103">_**主題上次修改日期：** 2013-02-12_</span><span class="sxs-lookup"><span data-stu-id="af5ef-103">_**Topic Last Modified:** 2013-02-12_</span></span>

<span data-ttu-id="af5ef-104">您可以傳送徽章、圖示或警示等形式的推播通知，即使行動應用程式處於非使用中時也能傳送給行動裝置。</span><span class="sxs-lookup"><span data-stu-id="af5ef-104">Push notifications, in the form of badges, icons, or alerts, can be sent to a mobile device even when the mobile application is inactive.</span></span> <span data-ttu-id="af5ef-105">推播通知會將事件（例如新的或未接的 IM 邀請及語音信箱）通知給使用者。</span><span class="sxs-lookup"><span data-stu-id="af5ef-105">Push notifications notify a user of events such as a new or missed IM invitation and voice mail.</span></span> <span data-ttu-id="af5ef-106">Lync Server 2013 行動裝置服務會將通知傳送到雲端式 Lync Server 推播通知服務，然後將通知傳送到 Apple 推播通知服務（APNS）（適用于執行 Lync 2010 行動用戶端的 Apple 裝置）或Microsoft 推播通知服務（MPNS）（適用于執行 Lync 2010 Mobile 或 Lync 2013 行動用戶端的 Windows Phone 裝置）。</span><span class="sxs-lookup"><span data-stu-id="af5ef-106">The Lync Server 2013 Mobility Service sends the notifications to the cloud-based Lync Server Push Notification Service, which then sends the notifications to the Apple Push Notification Service (APNS) (for an Apple device running the Lync 2010 Mobile client) or the Microsoft Push Notification Service (MPNS) (for a Windows Phone device running the Lync 2010 Mobile or the Lync 2013 Mobile client).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="af5ef-107">如果您使用 Windows Phone 搭配 Lync 2010 行動裝置或 Lync 2013 行動用戶端，推播通知就是一個重要的考慮。</span><span class="sxs-lookup"><span data-stu-id="af5ef-107">If you use Windows Phone with Lync 2010 Mobile or Lync 2013 Mobile client, push notification is an important consideration.</span></span><BR><span data-ttu-id="af5ef-108">如果您在 Apple 裝置上使用 Lync 2010 Mobile，推播通知就是一個重要的考慮。</span><span class="sxs-lookup"><span data-stu-id="af5ef-108">If you use Lync 2010 Mobile on Apple devices, push notification is an important consideration.</span></span><BR><span data-ttu-id="af5ef-109">如果您在 Apple 裝置上使用 Lync 2013 Mobile，就不再需要推播通知。</span><span class="sxs-lookup"><span data-stu-id="af5ef-109">If you use Lync 2013 Mobile on Apple devices, you no longer need push notification.</span></span>



</div>

<span data-ttu-id="af5ef-110">您可以執行下列動作，將拓撲設定為支援推播通知：</span><span class="sxs-lookup"><span data-stu-id="af5ef-110">Configure your topology to support push notifications by doing the following:</span></span>

  - <span data-ttu-id="af5ef-111">如果您的環境有 Lync Server 2010 或 Lync Server 2013 Edge 伺服器，您必須新增新的主機服務提供者、Microsoft Lync Online，然後在您的組織和 Lync Online 之間設定託管提供者同盟。</span><span class="sxs-lookup"><span data-stu-id="af5ef-111">If your environment has a Lync Server 2010 or Lync Server 2013 Edge Server, you need to add a new hosting provider, Microsoft Lync Online, and then set up hosting provider federation between your organization and Lync Online.</span></span>

  - <span data-ttu-id="af5ef-112">如果您的環境有 Office 通訊伺服器 2007 R2 Edge 伺服器，您必須使用 push.lync.com 設定直接 SIP 同盟。</span><span class="sxs-lookup"><span data-stu-id="af5ef-112">If your environment has a Office Communications Server 2007 R2 Edge Server, you need to set up direct SIP federation with push.lync.com.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="af5ef-113">Push.lync.com 是適用于推播通知服務的 Microsoft Office 365 網域。</span><span class="sxs-lookup"><span data-stu-id="af5ef-113">Push.lync.com is a Microsoft Office 365 domain for Push Notification Service.</span></span>

    
    </div>

  - <span data-ttu-id="af5ef-114">若要啟用推播通知，您必須執行**CsPushNotificationConfiguration** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="af5ef-114">To enable push notifications, you need to run the **Set-CsPushNotificationConfiguration** cmdlet.</span></span> <span data-ttu-id="af5ef-115">依預設，推播通知會關閉。</span><span class="sxs-lookup"><span data-stu-id="af5ef-115">By default, push notifications are turned off.</span></span>

  - <span data-ttu-id="af5ef-116">測試同盟設定和推播通知。</span><span class="sxs-lookup"><span data-stu-id="af5ef-116">Test the federation configuration and push notifications.</span></span>

<div>

## <a name="to-configure-for-push-notifications-with-lync-server-2013-or-lync-server-2010edge-server"></a><span data-ttu-id="af5ef-117">使用 Lync Server 2013 或 Lync Server 2010 Edge 伺服器來設定推播通知</span><span class="sxs-lookup"><span data-stu-id="af5ef-117">To configure for push notifications with Lync Server 2013 or Lync Server 2010 Edge Server</span></span>

1.  <span data-ttu-id="af5ef-118">登入 Lync Server 管理命令介面和 Ocscore 已安裝為 RtcUniversalServerAdmins 群組成員的電腦。</span><span class="sxs-lookup"><span data-stu-id="af5ef-118">Log on to a computer where Lync Server Management Shell and Ocscore are installed as a member of the RtcUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="af5ef-119">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="af5ef-119">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="af5ef-120">新增 Lync Server online 主機服務提供者。</span><span class="sxs-lookup"><span data-stu-id="af5ef-120">Add a Lync Server online hosting provider.</span></span> <span data-ttu-id="af5ef-121">在命令列中，輸入：</span><span class="sxs-lookup"><span data-stu-id="af5ef-121">At the command line, type:</span></span>
    
        New-CsHostingProvider -Identity <unique identifier for Lync Online hosting provider> -Enabled $True -ProxyFqdn <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
    
    <span data-ttu-id="af5ef-122">例如：</span><span class="sxs-lookup"><span data-stu-id="af5ef-122">For example:</span></span>
    
        New-CsHostingProvider -Identity "LyncOnline" -Enabled $True -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="af5ef-123">同一個主機名稱提供者不能有一個以上的同盟關聯。</span><span class="sxs-lookup"><span data-stu-id="af5ef-123">You cannot have more than one federation relationship with a single hosting provider.</span></span> <span data-ttu-id="af5ef-124">也就是說，如果您已設定與 sipfed.online.lync.com 具有同盟關聯的託管提供者，請不要針對其新增另一個主機服務提供者，即使主機提供者的身分識別是 LyncOnline 以外的內容。</span><span class="sxs-lookup"><span data-stu-id="af5ef-124">That is, if you have already set up a hosting provider that has a federation relationship with sipfed.online.lync.com, do not add another hosting provider for it, even if the identity of the hosting provider is something other than LyncOnline.</span></span>

    
    </div>

4.  <span data-ttu-id="af5ef-125">在您的組織與 Lync Online 的推播通知服務之間設定託管提供者同盟。</span><span class="sxs-lookup"><span data-stu-id="af5ef-125">Set up hosting provider federation between your organization and the Push Notification Service at Lync Online.</span></span> <span data-ttu-id="af5ef-126">在命令列中，輸入：</span><span class="sxs-lookup"><span data-stu-id="af5ef-126">At the command line, type:</span></span>
    
        New-CsAllowedDomain -Identity "push.lync.com"

</div>

<div>

## <a name="to-configure-for-push-notifications-with-office-communications-server-2007-r2edge-server"></a><span data-ttu-id="af5ef-127">使用 Office 通訊伺服器 2007 R2 Edge 伺服器來設定推播通知</span><span class="sxs-lookup"><span data-stu-id="af5ef-127">To configure for push notifications with Office Communications Server 2007 R2 Edge Server</span></span>

1.  <span data-ttu-id="af5ef-128">以 RtcUniversalServerAdmins 群組成員的身分登入邊緣伺服器。</span><span class="sxs-lookup"><span data-stu-id="af5ef-128">Log on to the Edge Server as a member of the RtcUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="af5ef-129">按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**管理工具**]，然後按一下 [**電腦管理**]。</span><span class="sxs-lookup"><span data-stu-id="af5ef-129">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **Computer Management**.</span></span>

3.  <span data-ttu-id="af5ef-130">在主控台樹中，展開 [**服務與應用程式**]，以滑鼠右鍵按一下 [ **Microsoft Office 通訊伺服器 2007 R2**]，然後按一下 [**屬性**]。</span><span class="sxs-lookup"><span data-stu-id="af5ef-130">In the console tree, expand **Services and Applications**, right-click **Microsoft Office Communications Server 2007 R2**, and then click **Properties**.</span></span>

4.  <span data-ttu-id="af5ef-131">按一下 [**允許**] 索引標籤上的 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="af5ef-131">On the **Allow** tab, click **Add**.</span></span>

5.  <span data-ttu-id="af5ef-132">在 [**新增聯盟合作夥伴**] 對話方塊中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="af5ef-132">In the **Add Federated Partner** dialog box, do the following:</span></span>
    
      - <span data-ttu-id="af5ef-133">在 [**聯盟夥伴功能變數名稱**] 中，輸入**push.lync.com**。</span><span class="sxs-lookup"><span data-stu-id="af5ef-133">In **Federated partner domain name**, type **push.lync.com**.</span></span>
    
      - <span data-ttu-id="af5ef-134">在 [**聯盟夥伴存取邊緣伺服器**] 中，輸入**sipfed.online.lync.com**。</span><span class="sxs-lookup"><span data-stu-id="af5ef-134">In **Federated partner Access Edge Server**, type **sipfed.online.lync.com**.</span></span>
    
      - <span data-ttu-id="af5ef-135">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="af5ef-135">Click **OK**.</span></span>

</div>

<div>

## <a name="to-enable-push-notifications"></a><span data-ttu-id="af5ef-136">啟用推播通知</span><span class="sxs-lookup"><span data-stu-id="af5ef-136">To enable push notifications</span></span>

1.  <span data-ttu-id="af5ef-137">登入 Lync Server 管理命令介面和 Ocscore 已安裝為 CsAdministrator 角色成員的電腦。</span><span class="sxs-lookup"><span data-stu-id="af5ef-137">Log on to a computer where Lync Server Management Shell and Ocscore are installed as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="af5ef-138">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="af5ef-138">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="af5ef-139">啟用推播通知。</span><span class="sxs-lookup"><span data-stu-id="af5ef-139">Enable push notifications.</span></span> <span data-ttu-id="af5ef-140">在命令列中，輸入：</span><span class="sxs-lookup"><span data-stu-id="af5ef-140">At the command line, type:</span></span>
    
        Set-CsPushNotificationConfiguration -EnableApplePushNotificationService $True -EnableMicrosoftPushNotificationService $True

4.  <span data-ttu-id="af5ef-141">啟用同盟。</span><span class="sxs-lookup"><span data-stu-id="af5ef-141">Enable federation.</span></span> <span data-ttu-id="af5ef-142">在命令列中，輸入：</span><span class="sxs-lookup"><span data-stu-id="af5ef-142">At the command line, type:</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

</div>

<div>

## <a name="to-test-federation-and-push-notifications"></a><span data-ttu-id="af5ef-143">測試同盟和推播通知</span><span class="sxs-lookup"><span data-stu-id="af5ef-143">To test federation and push notifications</span></span>

1.  <span data-ttu-id="af5ef-144">登入 Lync Server 管理命令介面和 Ocscore 已安裝為 CsAdministrator 角色成員的電腦。</span><span class="sxs-lookup"><span data-stu-id="af5ef-144">Log on to a computer where Lync Server Management Shell and Ocscore are installed as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="af5ef-145">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="af5ef-145">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="af5ef-146">測試同盟設定。</span><span class="sxs-lookup"><span data-stu-id="af5ef-146">Test the federation configuration.</span></span> <span data-ttu-id="af5ef-147">在命令列中，輸入：</span><span class="sxs-lookup"><span data-stu-id="af5ef-147">At the command line, type:</span></span>
    
        Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
    
    <span data-ttu-id="af5ef-148">例如：</span><span class="sxs-lookup"><span data-stu-id="af5ef-148">For example:</span></span>
    
        Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com

4.  <span data-ttu-id="af5ef-149">測試推播通知。</span><span class="sxs-lookup"><span data-stu-id="af5ef-149">Test push notifications.</span></span> <span data-ttu-id="af5ef-150">在命令列中，輸入：</span><span class="sxs-lookup"><span data-stu-id="af5ef-150">At the command line, type:</span></span>
    
        Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
    
    <span data-ttu-id="af5ef-151">例如：</span><span class="sxs-lookup"><span data-stu-id="af5ef-151">For example:</span></span>
    
        Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="af5ef-152">請參閱</span><span class="sxs-lookup"><span data-stu-id="af5ef-152">See Also</span></span>


[<span data-ttu-id="af5ef-153">Test-CsFederatedPartner</span><span class="sxs-lookup"><span data-stu-id="af5ef-153">Test-CsFederatedPartner</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner)  
[<span data-ttu-id="af5ef-154">Test-CsMcxPushNotification</span><span class="sxs-lookup"><span data-stu-id="af5ef-154">Test-CsMcxPushNotification</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxPushNotification)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

