---
title: Lync Server 2013：啟用 Lync-Skype 連線能力
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling Lync-Skype connectivity
ms:assetid: 34c4db3e-582f-41fb-85c4-3438ae02f09f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440170(v=OCS.15)
ms:contentKeyID: 57793361
ms.date: 12/16/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 43e26e54d0704ed009af1ef528e60979b759eb69
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528580"
---
# <a name="enabling-lync-skype-connectivity-in-lync-server-2013"></a>在 Lync Server 2013 中啟用 Lync-Skype 連線能力

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-12-16_

在您提交布建要求之後，您可以將重點放在 Lync Server 環境和設定 Lync-Skype 連線所需的管理工作上。 在本節中，我們假設 Lync Server 系統管理員已部署 Lync Server 和設定的外部存取。 如需設定 Lync Server 外部存取的詳細資訊，請參閱在 lync Server [2013 中規劃外部使用者存取](lync-server-2013-planning-for-external-user-access.md) 和 [部署 lync server 2013 中的外部使用者存取](lync-server-2013-deploying-external-user-access.md)。

若要準備 Lync Server 環境以進行 Lync-Skype 連線，Lync Server 系統管理員必須完成下列三項任務：

<div>

## <a name="1-configure-federation-and-pic"></a>1\. 設定同盟和 PIC

需要同盟才能讓 Skype 使用者能夠與您組織中的 Lync 使用者通訊。 公用立即訊息連線 (PIC) 是同盟的類別，必須設定為讓 Lync 使用者能夠與 Skype 使用者通訊。 同盟和 PIC 是使用 Lync Server 控制台進行設定，如下所示。

![顯示 PIC](images/Dn440170.451b94e3-0b38-488c-835f-1f25690e8074(OCS.15).jpg "顯示 PIC")

<div>


> [!IMPORTANT]  
> Live Communication Server 2005 SP1 或 Office 通訊伺服器2007不再支援 PIC 同盟。 支援的 PIC 同盟平臺包括 Lync Server 2013、Lync Server 2010 和 Office 通訊伺服器 2007 R2。



</div>

</div>

<div>

## <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a>2\. 設定至少一個原則以支援同盟使用者存取

使用 Lync Server 控制台，管理員必須設定一或多個外部使用者存取原則，以控制 Skype 使用者是否可以與內部 Lync Server 使用者共同作業。

![原則](images/Dn440170.8fd46ad1-9749-422c-8c47-c16ac9032cdb(OCS.15).jpg "原則")

</div>

<div>

## <a name="3-configure-the-skype-pic-provider-setting-for-lync"></a>3\. 設定 Lync 的 Skype PIC 提供者設定

使用 Lync Server 管理命令介面，管理員必須設定 Lync 用戶端原則，以將 Skype 顯示為其他 PIC 提供者。

<div>


> [!NOTE]  
>  (PIC) 服務提供者的公用立即訊息連線使用者無法參與您組織中的 IM 或音訊或視訊會議，除非您也在此程式中之前設定至少一個原則 (步驟2，) 以支援公用 IM 連線能力。



</div>

1.  若要設定同盟和 PIC，請參閱 at 中的「啟用或停用同盟和公用 IM 連線」 [https://go.microsoft.com/fwlink/p/?LinkId=306063](https://go.microsoft.com/fwlink/p/?linkid=306063) 。

2.  若要設定至少一個原則以支援同盟使用者存取，請參閱的「設定控制公用使用者存取的原則」 [https://go.microsoft.com/fwlink/p/?LinkId=306064](https://go.microsoft.com/fwlink/p/?linkid=306064) 。

**編輯現有的信使或 Skype PIC 提供者，並針對 Skype 進行設定**

1.  在 Lync Server 前端伺服器上，開啟 Lync Server 管理命令介面。

2.  執行下列兩個命令：
    
    `Remove-CsPublicProvider -Identity <identity-name>`
    
    <div>
    

    > [!NOTE]  
    > 如果您的環境中還沒有 PIC 提供者，且正在建立新的 PIC 提供者，則不需要執行 <STRONG>CsPublicProvider</STRONG> Cmdlet。

    
    </div>
    
    `New-CsPublicProvider -ProxyFqdn federation.messenger.msn.com -Enabled 1 -Identity Skype  -VerificationLevel 2 -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -IconUrl "https://images.edge.messenger.live.com/Messenger_16x16.png"`
    
    <div>
    

    > [!NOTE]  
    > 已新增于 Office 2013 中的 lync Server 2013 CU5 &amp; lync 桌面用戶端 SP1 中，NameDecorationRoutingDomain 和 NameDecorationExcludedDomainList 改善了 Lync 使用者新增所需的 skype 連絡人，以識別並路由傳送至 skype (： user (contoso.com) @msn .com) 的情況。 在 [新增 Skype 連絡人] 對話方塊中，這些新設定將允許自動設定位址使用者輸入的格式，NameDecorationRoutingDomain (應設定為 msn.com) 如果不包含 NameDecorationExcludedDomainList 中的網域 (我們目前可支援 msn.com、live.com、Hotmail.com、outlook.com) 。

    
    </div>

3.  在 Lync 用戶端中，您現在可以選取 [Skype] 作為 PIC 提供者，並透過指定其 Microsoft 帳戶來新增 Skype 用戶端。 此外，已使用其 Microsoft 帳戶進行合併和登入的 Skype 使用者，可將連絡人要求傳送給 Lync 使用者。 如需 Microsoft 帳戶的詳細資訊，請參閱 [什麼是 microsoft 帳戶？](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account)。 如需將用戶端新增至 Lync 的詳細資訊，請參閱 [在 Lync Server 2013 中使用 Lync-Skype 連線能力做為使用者](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)。
    
    ![新增 Skype 連絡人](images/Dn440170.df0e6ed9-2374-4dfa-a815-87281989487c(OCS.15).jpg "新增 Skype 連絡人")

4.  如需修改主控提供者的詳細資訊，請參閱 at 中的「建立或編輯主控的 SIP 同盟提供者」 [https://go.microsoft.com/fwlink/p/?LinkId=306065](https://go.microsoft.com/fwlink/p/?linkid=306065) 。

這會完成必須在伺服器上執行的管理工作。 您現在已設定 Lync-Skype 連線能力。

</div>

</div>

<span> </span>

</div>

</div>

</div>

