---
title: Lync Server 2013：啟用 Lync-Skype 連線功能
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
ms.openlocfilehash: 0125ff4719cd3dfeb65353df747395e596b45dac
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735813"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-lync-skype-connectivity-in-lync-server-2013"></a>在 Lync Server 2013 中啟用 Lync-Skype 連線功能

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-12-16_

在您提交提供要求之後，您就可以將焦點放在 Lync Server 環境，以及設定 Lync Skype 連線所需的管理工作上。 在本節中，我們假設 Lync Server 系統管理員已部署 Lync Server 並設定外部存取。 如需有關設定 Lync Server 外部存取的其他資訊，請參閱在 lync server [2013 中規劃外部使用者存取](lync-server-2013-planning-for-external-user-access.md)，以及[在 lync Server 2013 中部署外部使用者存取](lync-server-2013-deploying-external-user-access.md)。

若要準備 lync Server 環境以進行 Lync 與 Skype 連線，Lync Server 管理員必須完成下列三項工作：

<div>

## <a name="1-configure-federation-and-pic"></a>1。 設定同盟與 PIC

必須具備同盟，才能讓 Skype 使用者與您組織中的 Lync 使用者通訊。 公用立即訊息連線（PIC）是一種同盟類別，而且必須加以設定，才能讓 Lync 使用者與 Skype 使用者通訊。 [同盟] 和 [PIC] 是使用 Lync Server [控制台] 進行設定，如下所示。

![顯示 PIC](images/Dn440170.451b94e3-0b38-488c-835f-1f25690e8074(OCS.15).jpg "顯示 PIC")

<div>


> [!IMPORTANT]  
> 即時通訊伺服器 2005 SP1 或 Office 通訊伺服器2007不再支援 PIC 同盟。 適用于 PIC 同盟的支援平臺包括 Lync Server 2013、Lync Server 2010 及 Office 通訊伺服器 2007 R2。



</div>

</div>

<div>

## <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a>2。 至少設定一個要支援同盟使用者存取的原則

在 Lync Server [控制台] 中，系統管理員必須設定一或多個外部使用者存取原則，以控制 Skype 使用者是否可與內部 Lync 伺服器使用者共同作業。

![原則](images/Dn440170.8fd46ad1-9749-422c-8c47-c16ac9032cdb(OCS.15).jpg "原則")

</div>

<div>

## <a name="3-configure-the-skype-pic-provider-setting-for-lync"></a>3。 設定 Lync 的 Skype PIC 提供者設定

如果您使用 Lync Server 管理命令介面，系統管理員必須設定 Lync 用戶端原則，將 Skype 顯示為額外的 PIC 提供者。

<div>


> [!NOTE]  
> 公用立即訊息連線（PIC）服務提供者的使用者無法在您的組織中參與 IM 或音訊或視訊會議，除非您也設定了至少一項原則（在此程式中之前），以支援公用 IM 連線。



</div>

1.  若要設定同盟和 PIC，請參閱「啟用或停用同盟與公用 IM [http://go.microsoft.com/fwlink/p/?LinkId=306063](http://go.microsoft.com/fwlink/p/?linkid=306063)連線」。

2.  若要至少設定一個支援同盟使用者存取的原則，請參閱「設定控制公用使用者存取的原則」 [http://go.microsoft.com/fwlink/p/?LinkId=306064](http://go.microsoft.com/fwlink/p/?linkid=306064)。

**編輯現有的 Messenger 或 Skype PIC 提供者，並針對 Skype 進行設定**

1.  從 Lync Server 前端伺服器開啟 Lync Server 管理命令介面。

2.  執行下列兩個命令：
    
    `Remove-CsPublicProvider -Identity <identity-name>`
    
    <div>
    

    > [!NOTE]  
    > 如果您的環境中還沒有 PIC 提供者，且正在建立新的 PIC 提供者，則不需要執行<STRONG>CsPublicProvider</STRONG> Cmdlet。

    
    </div>
    
    `New-CsPublicProvider -ProxyFqdn federation.messenger.msn.com -Enabled 1 -Identity Skype  -VerificationLevel 2 -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -IconUrl "https://images.edge.messenger.live.com/Messenger_16x16.png"`
    
    <div>
    

    > [!NOTE]  
    > 在 Lync Server 2013 中新增&amp; OFFICE 2013 SP1 中的 CU5 lync 桌面用戶端，這會改善 lync 使用者新增必要的 skype 連絡人至「保密協定」，以找出並將其路由至 Skype （格式為：使用者（contoso .com） @msn .com）。 這些新設定可讓您在 [新增 Skype 連絡人] 對話方塊中的 [新增 Skype 連絡人] 對話方塊中，自動設定位址格式，但如果它不包含 NameDecorationExcludedDomainList 中的網域，則為 NameDecorationRoutingDomain （應設定為 msn.com）。我們目前可以支援 msn.com、live.com、Hotmail.com、outlook.com）。

    
    </div>

3.  您現在可以從 Lync 用戶端選取 [Skype] 作為 PIC 提供者，並透過指定其 Microsoft 帳戶來新增 Skype 用戶端。 此外，已透過其 Microsoft 帳戶合併並登入的 Skype 使用者，可以傳送聯絡人要求給 Lync 使用者。 如需 Microsoft 帳戶的詳細資訊，請參閱[什麼是 microsoft 帳戶？](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account)。 如需將用戶端新增至 Lync 的其他資訊，請參閱[在 Lync Server 2013 中使用 Lync Skype 連線功能做為最終使用者](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)。
    
    ![新增 Skype 連絡人](images/Dn440170.df0e6ed9-2374-4dfa-a815-87281989487c(OCS.15).jpg "新增 Skype 連絡人")

4.  如需有關修改託管提供者的詳細資訊，請參閱「建立或編輯託管 SIP [http://go.microsoft.com/fwlink/p/?LinkId=306065](http://go.microsoft.com/fwlink/p/?linkid=306065)聯盟提供者」。

這樣就完成了必須在伺服器上執行的系統管理工作。 您現在已設定 Lync-Skype 連線的連線。

</div>

</div>

<span> </span>

</div>

</div>

</div>

