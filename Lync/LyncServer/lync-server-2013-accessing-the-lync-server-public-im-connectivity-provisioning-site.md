---
title: 存取 Lync Server 公用 IM 連線布建網站
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Accessing the Lync Server public IM connectivity provisioning site
ms:assetid: 77a08234-6bcf-4f59-b43b-ee5fc1926585
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440174(v=OCS.15)
ms:contentKeyID: 57793364
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44692fd6267e23c98ecef1ca227cbde5289a44b5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191286"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="accessing-the-lync-server-public-im-connectivity-provisioning-site-from-lync-server-2013"></a>從 Lync Server 2013 存取 Lync Server 公用 IM 連線布建網站

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2019-03-22_

Lync-Skype 連線的布建處理已變更，與舊版的 PIC 布建方法相較。 此布建程式最多可能需要30天才能完成。 建議您先開始此程式，然後再完成本檔中的其餘步驟。 在您的帳戶中完成 Lync-Skype 布建程式之後，會啟用該帳戶，並為您的合格使用者啟用公用 IM 連線。

### <a name="to-provision-lync-skype-connectivity-you-need-the-following-information"></a>若要布建 Lync-Skype 連線性，您需要下列資訊：

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><ol>
<li><p>Microsoft 合約號碼</p></li>
<li><p>Access Edge service 完全限定功能變數名稱 (FQDN) </p></li>
<li><p>會話初始通訊協定 (SIP) 網域 (s) </p></li>
<li><p>任何其他的 Access Edge service Fqdn</p></li>
<li><p>連絡人資訊</p></li>
</ol></td>
</tr>
</tbody>
</table>

從2019年4月開始，我們將停止透過 pic.lync.com 網站為 Skype 同盟布建之客戶的連絡人資訊的收集和保留。 進行此變更是為了確保 pic.lync.com 布建系統遵守 Microsoft 隱私權原則。 

這種變更生效後，我們將無法再在暫止的布建變更上提供電子郵件更新。 PIC 布建變更通常會在進入之後的24-48 小時內完成。 如果您在提交布建要求之後仍會出現48小時的 Skype 同盟問題，請與 Microsoft 技術支援人員接洽，以進一步調查。

> [!IMPORTANT]
> 做為此變更的一部分，所有先前輸入的連絡人資訊都會在2019年4月結束時從系統中清除。

### <a name="to-initiate-the-provisioning-process-for-lync-skype-connectivity"></a>若要啟動 Lync-Skype 連線的布建過程：

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><ol>
<li><p><strong>https://pic.lync.com</strong>使用您的 Microsoft Windows LIVE ID 登入網站。</p></li>
<li><p>選取 [Microsoft 授權合約] 類型。</p></li>
<li><p>選取 [確認您已讀取並接受 Lync 伺服器的產品使用權力] 核取方塊。</p></li>
<li><p>在 [ <strong>啟動</strong> 布建要求] 頁面上，按一下適當的連結，以啟動布建要求：</p></li>
<li><p>在 [ <strong>指定供給資訊</strong> ] 頁面上，輸入 <strong>ACCESS Edge service FQDN</strong>。 例如， <strong>sip.contoso.com</strong>。</p>



> [!IMPORTANT]
> 2017年7月1日之後，Microsoft 將會另外要求客戶已部署用於公用 IM 連線的同盟 DNS SRV 記錄，以繼續運作。

</li>
<li><p>輸入至少一或多個 SIP 功能變數名稱，然後按一下 [ <strong>新增</strong>]。</p>



> [!IMPORTANT]
> 必須至少有一個 Access Edge server 與一個 SIP 網域，才可完成布建程式。 SIP 網域和 Access Edge server 在網路上必須是作用中、運作且可連線。

</li>
<li><p>在 <strong>公用 IM 服務提供者</strong>的清單中，選取 [ <strong>Skype]，</strong> 然後按一下 <strong>[下一步]</strong> ，新增連絡人資訊，並提交布建要求。</p></li>
</ol></td>
</tr>
</tbody>
</table>


在提交布建要求之後，最多可能需要30天的時間才能啟用該帳戶，且啟用使用者來進行公用 IM 連線。

<div>

## <a name="enabling-federation-and-public-im-connectivity-pic"></a>啟用同盟和公用 IM 連線 (PIC) 

在您提交布建要求之後，您可以將重點放在 Lync Server 環境和設定 Lync-Skype 連線所需的管理工作上。 在本節中，我們假設 Lync Server 系統管理員已部署 Lync Server 和設定的外部存取。 如需設定 Lync Server 的外部存取的詳細資訊，請參閱的「規劃外部使用者存取」 [https://go.microsoft.com/fwlink/p/?LinkID=273772](https://go.microsoft.com/fwlink/p/?linkid=273772) 和「部署外部使用者存取」 [https://go.microsoft.com/fwlink/p/?LinkID=27378](https://go.microsoft.com/fwlink/p/?linkid=27378) 。

若要準備 Lync Server 環境以進行 Lync-Skype 連線，Lync Server 系統管理員必須完成下列三項任務：

<div>

## <a name="1-configure-federation-and-pic"></a>1\. 設定同盟和 PIC

需要同盟才能讓 Skype 使用者能夠與您組織中的 Lync 使用者通訊。 公用立即訊息連線 (PIC) 是同盟的類別，必須設定為讓 Lync 使用者能夠與 Skype 使用者通訊。 同盟和 PIC 是使用 Lync Server 控制台進行設定，如下所示。

<div>


> [!IMPORTANT]
> Live Communication Server 2005 SP1 或 Office 通訊伺服器2007不再支援 PIC 同盟。 支援的 PIC 同盟平臺包括 Lync Server 2013、Lync Server 2010 和 Office 通訊伺服器 2007 R2。



</div>

</div>

<div>

## <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a>2\. 設定至少一個原則以支援同盟使用者存取

使用 Lync Server 控制台，管理員必須設定一或多個外部使用者存取原則，以控制 Skype 使用者是否可以與內部 Lync Server 使用者共同作業。

</div>

<div>

## <a name="3-configure-the-skype-pic-provider-setting-for-lync"></a>3\. 設定 Lync 的 Skype PIC 提供者設定

使用 Lync Server 管理命令介面，管理員必須設定 Lync 用戶端原則，以將 Skype 顯示為其他 PIC 提供者。

<div>


> [!NOTE]
>  (PIC) 服務提供者的公用立即訊息連線使用者無法參與您組織中的 IM 或會議，除非您在此程式之前設定至少一個原則 (步驟2，) 以支援公用 IM 連線能力。<BR>若要設定同盟和 PIC，請參閱 at 中的「啟用或停用同盟和公用 IM 連線」 <A href="https://go.microsoft.com/fwlink/p/?linkid=306063">https://go.microsoft.com/fwlink/p/?LinkId=306063</A> 。<BR>若要設定至少一個原則以支援同盟使用者存取，請參閱的「設定控制公用使用者存取的原則」 <A href="https://go.microsoft.com/fwlink/p/?linkid=306064">https://go.microsoft.com/fwlink/p/?LinkId=306064</A> 。



</div>

1.  在 Lync Server 前端伺服器上，開啟 Lync Server 管理命令介面。

2.  執行下列兩個命令：
    
      - `Remove-CsPublicProvider -Identity <identity-name>`
        
        <div>
        

        > [!NOTE]
        > 如果您的環境中還沒有 PIC 提供者，且正在建立新的 PIC 提供者，則不需要執行 <STRONG>CsPublicProvider</STRONG> Cmdlet。

        
        </div>
    
      - `New-CsPublicProvider -ProxyFqdn federation.messenger.msn.com -Enabled 1 -Identity Skype  -VerificationLevel 2 -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -IconUrl "https://images.edge.messenger.live.com/Messenger_16x16.png"`
        
        <div>
        

        > [!NOTE]
        > 已新增于 Office 2013 中的 lync Server 2013 CU5 &amp; lync 桌面用戶端 SP1 中，NameDecorationRoutingDomain 和 NameDecorationExcludedDomainList 改善了 Lync 使用者新增所需的 skype 連絡人，以識別並路由傳送至 skype (： user (contoso.com) @msn .com) 的情況。 在 [新增 Skype 連絡人] 對話方塊中，這些新設定將允許自動設定位址使用者輸入的格式，NameDecorationRoutingDomain (應設定為 msn.com) 如果不包含 NameDecorationExcludedDomainList 中的網域 (我們目前可支援 msn.com、live.com、Hotmail.com、outlook.com) 。

        
        </div>

3.  在 Lync 用戶端中，您現在可以選取 [Skype] 作為 PIC 提供者，並透過指定其 Microsoft 帳戶來新增 Skype 用戶端。 此外，已使用其 Microsoft 帳戶進行合併和登入的 Skype 使用者，可將連絡人要求傳送給 Lync 使用者。 如需 Microsoft 帳戶的詳細資訊，請參閱 [什麼是 microsoft 帳戶？](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account)。 如需將用戶端新增至 Lync 的詳細資訊，請參閱 [在 Lync Server 2013 中使用 Lync-Skype 連線能力做為使用者](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)。

4.  如需修改主控提供者的詳細資訊，請參閱 at 中的「建立或編輯主控的 SIP 同盟提供者」 [https://go.microsoft.com/fwlink/p/?LinkId=306065](https://go.microsoft.com/fwlink/p/?linkid=306065) 。

這會完成必須在伺服器上執行的管理工作。 您現在已設定 Lync-Skype 連線能力。

</div>

</div>

<div>

## <a name="additional-resources"></a>其他資源

[在 Lync Server 2013 中使用 Lync-Skype 連線能力做為使用者](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)

[Lync Server 2013 中的 Lync-Skype 連線布配指南](lync-server-2013-provisioning-guide-for-lync-skype-connectivity.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

