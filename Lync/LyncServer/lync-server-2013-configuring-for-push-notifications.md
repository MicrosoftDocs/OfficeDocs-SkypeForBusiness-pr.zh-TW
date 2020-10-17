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
ms.openlocfilehash: 4f68cafcfcc616bd6e467514704416f134de3665
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517490"
---
# <a name="configuring-for-push-notifications-in-lync-server-2013"></a><span data-ttu-id="6990b-102">在 Lync Server 2013 中設定推播通知</span><span class="sxs-lookup"><span data-stu-id="6990b-102">Configuring for push notifications in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6990b-103">_**主題上次修改日期：** 2013-02-12_</span><span class="sxs-lookup"><span data-stu-id="6990b-103">_**Topic Last Modified:** 2013-02-12_</span></span>

<span data-ttu-id="6990b-104">即使當行動應用程式非使用中時，也可以將「徽章」、圖示或警示等推播通知傳送給行動裝置。</span><span class="sxs-lookup"><span data-stu-id="6990b-104">Push notifications, in the form of badges, icons, or alerts, can be sent to a mobile device even when the mobile application is inactive.</span></span> <span data-ttu-id="6990b-105">推播通知會通知使用者有新的或錯過的 IM 邀請和語音信箱等事件。</span><span class="sxs-lookup"><span data-stu-id="6990b-105">Push notifications notify a user of events such as a new or missed IM invitation and voice mail.</span></span> <span data-ttu-id="6990b-106">Lync Server 2013 行動性服務會將通知傳送至雲端型 Lync Server 推播通知服務，然後針對執行 lync 2010 行動用戶端) 或 Microsoft 推播通知服務，針對執行 Lync 2010 行動裝置或 Lync 2013 行動用戶端 (的 Windows Phone 裝置，將通知傳送給 Apple Push Notification Service (APNS)  (。</span><span class="sxs-lookup"><span data-stu-id="6990b-106">The Lync Server 2013 Mobility Service sends the notifications to the cloud-based Lync Server Push Notification Service, which then sends the notifications to the Apple Push Notification Service (APNS) (for an Apple device running the Lync 2010 Mobile client) or the Microsoft Push Notification Service (MPNS) (for a Windows Phone device running the Lync 2010 Mobile or the Lync 2013 Mobile client).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6990b-107">如果您使用 Windows Phone 搭配 Lync 2010 行動裝置或 Lync 2013 行動用戶端，推播通知是一個重要的考慮。</span><span class="sxs-lookup"><span data-stu-id="6990b-107">If you use Windows Phone with Lync 2010 Mobile or Lync 2013 Mobile client, push notification is an important consideration.</span></span><BR><span data-ttu-id="6990b-108">如果您在 Apple 裝置上使用 Lync 2010 Mobile，推播通知是一個重要的考慮。</span><span class="sxs-lookup"><span data-stu-id="6990b-108">If you use Lync 2010 Mobile on Apple devices, push notification is an important consideration.</span></span><BR><span data-ttu-id="6990b-109">如果您在 Apple 裝置上使用 Lync 2013 行動裝置，則不再需要推播通知。</span><span class="sxs-lookup"><span data-stu-id="6990b-109">If you use Lync 2013 Mobile on Apple devices, you no longer need push notification.</span></span>



</div>

<span data-ttu-id="6990b-110">執行下列動作，將拓撲設定為支援推播通知：</span><span class="sxs-lookup"><span data-stu-id="6990b-110">Configure your topology to support push notifications by doing the following:</span></span>

  - <span data-ttu-id="6990b-111">如果您的環境具有 Lync Server 2010 或 Lync Server 2013 Edge Server，您必須新增主機服務提供者（Microsoft Lync Online），然後在您的組織和 Lync Online 之間設定裝載提供者同盟。</span><span class="sxs-lookup"><span data-stu-id="6990b-111">If your environment has a Lync Server 2010 or Lync Server 2013 Edge Server, you need to add a new hosting provider, Microsoft Lync Online, and then set up hosting provider federation between your organization and Lync Online.</span></span>

  - <span data-ttu-id="6990b-112">如果您的環境具有 Office 通訊伺服器 2007 R2 Edge Server，您必須設定與 push.lync.com 的直接 SIP 同盟。</span><span class="sxs-lookup"><span data-stu-id="6990b-112">If your environment has a Office Communications Server 2007 R2 Edge Server, you need to set up direct SIP federation with push.lync.com.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6990b-113">Push.lync.com 是推播通知服務的 Microsoft Office 365 網域。</span><span class="sxs-lookup"><span data-stu-id="6990b-113">Push.lync.com is a Microsoft Office 365 domain for Push Notification Service.</span></span>

    
    </div>

  - <span data-ttu-id="6990b-114">若要啟用推播通知，您必須執行 **Set-CsPushNotificationConfiguration** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="6990b-114">To enable push notifications, you need to run the **Set-CsPushNotificationConfiguration** cmdlet.</span></span> <span data-ttu-id="6990b-115">依預設，推播通知會關閉。</span><span class="sxs-lookup"><span data-stu-id="6990b-115">By default, push notifications are turned off.</span></span>

  - <span data-ttu-id="6990b-116">測試同盟設定和推播通知。</span><span class="sxs-lookup"><span data-stu-id="6990b-116">Test the federation configuration and push notifications.</span></span>

<div>

## <a name="to-configure-for-push-notifications-with-lync-server-2013-or-lync-server-2010edge-server"></a><span data-ttu-id="6990b-117">使用 Lync Server 2013 或 Lync Server 2010 Edge Server 設定推播通知</span><span class="sxs-lookup"><span data-stu-id="6990b-117">To configure for push notifications with Lync Server 2013 or Lync Server 2010 Edge Server</span></span>

1.  <span data-ttu-id="6990b-118">登入 Lync Server 管理命令介面和 Ocscore.msi 已安裝成 RtcUniversalServerAdmins 群組成員的電腦。</span><span class="sxs-lookup"><span data-stu-id="6990b-118">Log on to a computer where Lync Server Management Shell and Ocscore are installed as a member of the RtcUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="6990b-119">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="6990b-119">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="6990b-120">新增 Lync Server online 主機服務提供者。</span><span class="sxs-lookup"><span data-stu-id="6990b-120">Add a Lync Server online hosting provider.</span></span> <span data-ttu-id="6990b-121">在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="6990b-121">At the command line, type:</span></span>
    
        New-CsHostingProvider -Identity <unique identifier for Lync Online hosting provider> -Enabled $True -ProxyFqdn <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
    
    <span data-ttu-id="6990b-122">例如：</span><span class="sxs-lookup"><span data-stu-id="6990b-122">For example:</span></span>
    
        New-CsHostingProvider -Identity "LyncOnline" -Enabled $True -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6990b-123">您不能有一個以上的「裝載提供者」的同盟關係。</span><span class="sxs-lookup"><span data-stu-id="6990b-123">You cannot have more than one federation relationship with a single hosting provider.</span></span> <span data-ttu-id="6990b-124">也就是說，如果您已設定與 sipfed.online.lync.com 具有同盟關聯的裝載提供者，請勿為其新增其他主機服務提供者，即使主機服務的身分識別是 Nm-lynconline-w15-long 以外的其他專案。</span><span class="sxs-lookup"><span data-stu-id="6990b-124">That is, if you have already set up a hosting provider that has a federation relationship with sipfed.online.lync.com, do not add another hosting provider for it, even if the identity of the hosting provider is something other than LyncOnline.</span></span>

    
    </div>

4.  <span data-ttu-id="6990b-125">在 Lync Online 上設定組織與推播通知服務之間的裝載提供者同盟。</span><span class="sxs-lookup"><span data-stu-id="6990b-125">Set up hosting provider federation between your organization and the Push Notification Service at Lync Online.</span></span> <span data-ttu-id="6990b-126">在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="6990b-126">At the command line, type:</span></span>
    
        New-CsAllowedDomain -Identity "push.lync.com"

</div>

<div>

## <a name="to-configure-for-push-notifications-with-office-communications-server-2007-r2edge-server"></a><span data-ttu-id="6990b-127">若要使用 Office 通訊伺服器 2007 R2 Edge Server 設定推播通知</span><span class="sxs-lookup"><span data-stu-id="6990b-127">To configure for push notifications with Office Communications Server 2007 R2 Edge Server</span></span>

1.  <span data-ttu-id="6990b-128">以 RtcUniversalServerAdmins 群組成員的身分登入 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="6990b-128">Log on to the Edge Server as a member of the RtcUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="6990b-129">依序按一下 [ **開始**]、[ **所有程式**]、[系統管理 **工具**] 及 [ **電腦管理**]。</span><span class="sxs-lookup"><span data-stu-id="6990b-129">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **Computer Management**.</span></span>

3.  <span data-ttu-id="6990b-130">在主控台樹中，展開 [**服務及應用程式**]，再以滑鼠**按右鍵 [** **Microsoft Office 通訊伺服器 2007 R2**]，然後按一下 [內容]。</span><span class="sxs-lookup"><span data-stu-id="6990b-130">In the console tree, expand **Services and Applications**, right-click **Microsoft Office Communications Server 2007 R2**, and then click **Properties**.</span></span>

4.  <span data-ttu-id="6990b-131">在 [ **允許** ] 索引標籤上，按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="6990b-131">On the **Allow** tab, click **Add**.</span></span>

5.  <span data-ttu-id="6990b-132">在 [ **新增同盟合作夥伴** ] 對話方塊中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="6990b-132">In the **Add Federated Partner** dialog box, do the following:</span></span>
    
      - <span data-ttu-id="6990b-133">在 [同盟 **夥伴功能變數名稱**] 中，輸入 **push.lync.com**。</span><span class="sxs-lookup"><span data-stu-id="6990b-133">In **Federated partner domain name**, type **push.lync.com**.</span></span>
    
      - <span data-ttu-id="6990b-134">在 [同盟 **Partner Access Edge Server**] 中，輸入 **sipfed.online.lync.com**。</span><span class="sxs-lookup"><span data-stu-id="6990b-134">In **Federated partner Access Edge Server**, type **sipfed.online.lync.com**.</span></span>
    
      - <span data-ttu-id="6990b-135">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6990b-135">Click **OK**.</span></span>

</div>

<div>

## <a name="to-enable-push-notifications"></a><span data-ttu-id="6990b-136">啟用推播通知</span><span class="sxs-lookup"><span data-stu-id="6990b-136">To enable push notifications</span></span>

1.  <span data-ttu-id="6990b-137">登入 Lync Server 管理命令介面和 Ocscore.msi 已安裝為 CsAdministrator role 成員的電腦。</span><span class="sxs-lookup"><span data-stu-id="6990b-137">Log on to a computer where Lync Server Management Shell and Ocscore are installed as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="6990b-138">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="6990b-138">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="6990b-139">啟用推播通知。</span><span class="sxs-lookup"><span data-stu-id="6990b-139">Enable push notifications.</span></span> <span data-ttu-id="6990b-140">在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="6990b-140">At the command line, type:</span></span>
    
        Set-CsPushNotificationConfiguration -EnableApplePushNotificationService $True -EnableMicrosoftPushNotificationService $True

4.  <span data-ttu-id="6990b-141">啟用同盟。</span><span class="sxs-lookup"><span data-stu-id="6990b-141">Enable federation.</span></span> <span data-ttu-id="6990b-142">在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="6990b-142">At the command line, type:</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

</div>

<div>

## <a name="to-test-federation-and-push-notifications"></a><span data-ttu-id="6990b-143">測試同盟及推播通知</span><span class="sxs-lookup"><span data-stu-id="6990b-143">To test federation and push notifications</span></span>

1.  <span data-ttu-id="6990b-144">登入 Lync Server 管理命令介面和 Ocscore.msi 已安裝為 CsAdministrator role 成員的電腦。</span><span class="sxs-lookup"><span data-stu-id="6990b-144">Log on to a computer where Lync Server Management Shell and Ocscore are installed as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="6990b-145">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="6990b-145">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="6990b-146">測試同盟設定。</span><span class="sxs-lookup"><span data-stu-id="6990b-146">Test the federation configuration.</span></span> <span data-ttu-id="6990b-147">在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="6990b-147">At the command line, type:</span></span>
    
        Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
    
    <span data-ttu-id="6990b-148">例如：</span><span class="sxs-lookup"><span data-stu-id="6990b-148">For example:</span></span>
    
        Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com

4.  <span data-ttu-id="6990b-149">測試推入通知。</span><span class="sxs-lookup"><span data-stu-id="6990b-149">Test push notifications.</span></span> <span data-ttu-id="6990b-150">在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="6990b-150">At the command line, type:</span></span>
    
        Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
    
    <span data-ttu-id="6990b-151">例如：</span><span class="sxs-lookup"><span data-stu-id="6990b-151">For example:</span></span>
    
        Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6990b-152">請參閱</span><span class="sxs-lookup"><span data-stu-id="6990b-152">See Also</span></span>


[<span data-ttu-id="6990b-153">Test-CsFederatedPartner</span><span class="sxs-lookup"><span data-stu-id="6990b-153">Test-CsFederatedPartner</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner)  
[<span data-ttu-id="6990b-154">Test-CsMcxPushNotification</span><span class="sxs-lookup"><span data-stu-id="6990b-154">Test-CsMcxPushNotification</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxPushNotification)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

