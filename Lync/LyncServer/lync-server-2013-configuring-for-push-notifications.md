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

# <a name="configuring-for-push-notifications-in-lync-server-2013"></a>在 Lync Server 2013 中設定推播通知

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-12_

您可以傳送徽章、圖示或警示等形式的推播通知，即使行動應用程式處於非使用中時也能傳送給行動裝置。 推播通知會將事件（例如新的或未接的 IM 邀請及語音信箱）通知給使用者。 Lync Server 2013 行動裝置服務會將通知傳送到雲端式 Lync Server 推播通知服務，然後將通知傳送到 Apple 推播通知服務（APNS）（適用于執行 Lync 2010 行動用戶端的 Apple 裝置）或Microsoft 推播通知服務（MPNS）（適用于執行 Lync 2010 Mobile 或 Lync 2013 行動用戶端的 Windows Phone 裝置）。

<div>


> [!IMPORTANT]  
> 如果您使用 Windows Phone 搭配 Lync 2010 行動裝置或 Lync 2013 行動用戶端，推播通知就是一個重要的考慮。<BR>如果您在 Apple 裝置上使用 Lync 2010 Mobile，推播通知就是一個重要的考慮。<BR>如果您在 Apple 裝置上使用 Lync 2013 Mobile，就不再需要推播通知。



</div>

您可以執行下列動作，將拓撲設定為支援推播通知：

  - 如果您的環境有 Lync Server 2010 或 Lync Server 2013 Edge 伺服器，您必須新增新的主機服務提供者、Microsoft Lync Online，然後在您的組織和 Lync Online 之間設定託管提供者同盟。

  - 如果您的環境有 Office 通訊伺服器 2007 R2 Edge 伺服器，您必須使用 push.lync.com 設定直接 SIP 同盟。
    
    <div>
    

    > [!NOTE]  
    > Push.lync.com 是適用于推播通知服務的 Microsoft Office 365 網域。

    
    </div>

  - 若要啟用推播通知，您必須執行**CsPushNotificationConfiguration** Cmdlet。 依預設，推播通知會關閉。

  - 測試同盟設定和推播通知。

<div>

## <a name="to-configure-for-push-notifications-with-lync-server-2013-or-lync-server-2010edge-server"></a>使用 Lync Server 2013 或 Lync Server 2010 Edge 伺服器來設定推播通知

1.  登入 Lync Server 管理命令介面和 Ocscore 已安裝為 RtcUniversalServerAdmins 群組成員的電腦。

2.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  新增 Lync Server online 主機服務提供者。 在命令列中，輸入：
    
        New-CsHostingProvider -Identity <unique identifier for Lync Online hosting provider> -Enabled $True -ProxyFqdn <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
    
    例如：
    
        New-CsHostingProvider -Identity "LyncOnline" -Enabled $True -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
    
    <div>
    

    > [!NOTE]  
    > 同一個主機名稱提供者不能有一個以上的同盟關聯。 也就是說，如果您已設定與 sipfed.online.lync.com 具有同盟關聯的託管提供者，請不要針對其新增另一個主機服務提供者，即使主機提供者的身分識別是 LyncOnline 以外的內容。

    
    </div>

4.  在您的組織與 Lync Online 的推播通知服務之間設定託管提供者同盟。 在命令列中，輸入：
    
        New-CsAllowedDomain -Identity "push.lync.com"

</div>

<div>

## <a name="to-configure-for-push-notifications-with-office-communications-server-2007-r2edge-server"></a>使用 Office 通訊伺服器 2007 R2 Edge 伺服器來設定推播通知

1.  以 RtcUniversalServerAdmins 群組成員的身分登入邊緣伺服器。

2.  按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**管理工具**]，然後按一下 [**電腦管理**]。

3.  在主控台樹中，展開 [**服務與應用程式**]，以滑鼠右鍵按一下 [ **Microsoft Office 通訊伺服器 2007 R2**]，然後按一下 [**屬性**]。

4.  按一下 [**允許**] 索引標籤上的 [**新增**]。

5.  在 [**新增聯盟合作夥伴**] 對話方塊中，執行下列動作：
    
      - 在 [**聯盟夥伴功能變數名稱**] 中，輸入**push.lync.com**。
    
      - 在 [**聯盟夥伴存取邊緣伺服器**] 中，輸入**sipfed.online.lync.com**。
    
      - 按一下 [確定]****。

</div>

<div>

## <a name="to-enable-push-notifications"></a>啟用推播通知

1.  登入 Lync Server 管理命令介面和 Ocscore 已安裝為 CsAdministrator 角色成員的電腦。

2.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  啟用推播通知。 在命令列中，輸入：
    
        Set-CsPushNotificationConfiguration -EnableApplePushNotificationService $True -EnableMicrosoftPushNotificationService $True

4.  啟用同盟。 在命令列中，輸入：
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

</div>

<div>

## <a name="to-test-federation-and-push-notifications"></a>測試同盟和推播通知

1.  登入 Lync Server 管理命令介面和 Ocscore 已安裝為 CsAdministrator 角色成員的電腦。

2.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  測試同盟設定。 在命令列中，輸入：
    
        Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
    
    例如：
    
        Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com

4.  測試推播通知。 在命令列中，輸入：
    
        Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
    
    例如：
    
        Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com

</div>

<div>

## <a name="see-also"></a>請參閱


[Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner)  
[Test-CsMcxPushNotification](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxPushNotification)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

