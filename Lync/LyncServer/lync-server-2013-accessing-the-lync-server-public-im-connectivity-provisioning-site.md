---
title: 存取 Lync Server 公用 IM 連線佈建網站
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
ms.openlocfilehash: dbcb2e46380e7ed4bbd8499e83f638cb314844e9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723383"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="accessing-the-lync-server-public-im-connectivity-provisioning-site-from-lync-server-2013"></a>透過 Lync Server 2013 存取 Lync Server 公用 IM 連線佈建網站

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2019-03-22_

Lync-Skype 連線的提供程式已變更，與先前的 PIC 自動設定方法相比。 此設定程式可能需要長達三十天才能完成。 我們建議您先開始這個程式，然後再完成這份檔中的其餘步驟。 針對您的帳戶完成 Lync Skype 預配程式後，該帳戶即會啟用，且您的合格使用者可供公用 IM 連線。

### <a name="to-provision-lync-skype-connectivity-you-need-the-following-information"></a>若要設定 Lync-Skype 連線性，您需要下列資訊：

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><ol>
<li><p>Microsoft 協定編號</p></li>
<li><p>Access Edge 服務的完整功能變數名稱（FQDN）</p></li>
<li><p>會話初始通訊協定（SIP）網域</p></li>
<li><p>任何其他存取邊緣服務 Fqdn</p></li>
<li><p>連絡人資訊</p></li>
</ol></td>
</tr>
</tbody>
</table>

從2019年4月開始，我們會針對透過 pic.lync.com 網站提供 Skype Federation 的客戶停止收集及保留連絡人資訊。 我們正在進行這種變更，以確保 pic.lync.com 置備系統符合 Microsoft 隱私權原則。 

此變更生效之後，我們將無法在未決的置備變更上提供電子郵件更新。 PIC 置備變更通常會在輸入後的24-48 小時內完成。 如果您在提交提供要求之後，仍會遇到48小時的 Skype Federation 問題，請與 Microsoft 技術支援人員聯繫，以進一步調查。

> [!IMPORTANT]
> 如此一來，在2019年4月結束後，所有先前輸入的連絡人資訊都會從我們的系統中清除。

### <a name="to-initiate-the-provisioning-process-for-lync-skype-connectivity"></a>若要啟動 Lync Skype 連線的置備程式：

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><ol>
<li><p>使用您的 Microsoft Windows Live <strong>https://pic.lync.com</strong>ID 登入網站。</p></li>
<li><p>選取 Microsoft 授權合約類型。</p></li>
<li><p>選取核取方塊，確認您已閱讀並接受 Lync Server 的產品使用權力。</p></li>
<li><p>在 [<strong>啟動提供要求</strong>] 頁面上，按一下適當的連結以啟動提供要求：</p></li>
<li><p>在 [<strong>指定供給資訊</strong>] 頁面上，輸入<strong>存取邊緣服務 FQDN</strong>。 例如， <strong>sip.contoso.com</strong>。</p>



> [!IMPORTANT]
> 2017年7月1日之後，Microsoft 會進一步要求客戶提供公用 IM 連線的同盟 DNS SRV 記錄來繼續運作。

</li>
<li><p>輸入至少一個或多個 SIP 功能變數名稱，然後按一下 [<strong>新增</strong>]。</p>



> [!IMPORTANT]
> 至少需要一個存取邊緣伺服器和一個 SIP 網域，才能完成置備程式。 SIP 網域和存取邊緣伺服器在網路上必須是作用中、正常運作且可存取的。

</li>
<li><p>在<strong>公用 IM 服務提供者</strong>清單中，選取 [ <strong>Skype]，</strong>然後按一下<strong>[下一步]</strong>以新增連絡人資訊，並提交置備要求。</p></li>
</ol></td>
</tr>
</tbody>
</table>


在提交預配要求之後，最多可能需要30天的時間，才能啟動該帳戶，以及啟用公用 IM 連線的使用者。

<div>

## <a name="enabling-federation-and-public-im-connectivity-pic"></a>啟用同盟與公用 IM 連線（PIC）

在您提交提供要求之後，您就可以將焦點放在 Lync Server 環境，以及設定 Lync Skype 連線所需的管理工作上。 在本節中，我們假設 Lync Server 系統管理員已部署 Lync Server 並設定外部存取。 如需有關設定 Lync Server 外部存取的其他資訊，請參閱「規劃外部使用者存取」 [https://go.microsoft.com/fwlink/p/?LinkID=273772](https://go.microsoft.com/fwlink/p/?linkid=273772)和「部署外部使用者存取」 [https://go.microsoft.com/fwlink/p/?LinkID=27378](https://go.microsoft.com/fwlink/p/?linkid=27378)。

若要準備 lync Server 環境以進行 Lync 與 Skype 連線，Lync Server 管理員必須完成下列三項工作：

<div>

## <a name="1-configure-federation-and-pic"></a>1。 設定同盟與 PIC

必須具備同盟，才能讓 Skype 使用者與您組織中的 Lync 使用者通訊。 公用立即訊息連線（PIC）是一種同盟類別，而且必須加以設定，才能讓 Lync 使用者與 Skype 使用者通訊。 [同盟] 和 [PIC] 是使用 Lync Server [控制台] 進行設定，如下所示。

<div>


> [!IMPORTANT]
> 即時通訊伺服器 2005 SP1 或 Office 通訊伺服器2007不再支援 PIC 同盟。 適用于 PIC 同盟的支援平臺包括 Lync Server 2013、Lync Server 2010 及 Office 通訊伺服器 2007 R2。



</div>

</div>

<div>

## <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a>2。 至少設定一個要支援同盟使用者存取的原則

在 Lync Server [控制台] 中，系統管理員必須設定一或多個外部使用者存取原則，以控制 Skype 使用者是否可與內部 Lync 伺服器使用者共同作業。

</div>

<div>

## <a name="3-configure-the-skype-pic-provider-setting-for-lync"></a>3。 設定 Lync 的 Skype PIC 提供者設定

如果您使用 Lync Server 管理命令介面，系統管理員必須設定 Lync 用戶端原則，將 Skype 顯示為額外的 PIC 提供者。

<div>


> [!NOTE]
> 公用立即訊息連線（PIC）服務提供者的使用者無法在您的組織中參與 IM 或會議，除非您在此程式中設定至少一個原則（步驟2），才能支援公用 IM 連線。<BR>若要設定同盟和 PIC，請參閱「啟用或停用同盟與公用 IM <A href="https://go.microsoft.com/fwlink/p/?linkid=306063">https://go.microsoft.com/fwlink/p/?LinkId=306063</A>連線」。<BR>若要至少設定一個支援同盟使用者存取的原則，請參閱「設定控制公用使用者存取的原則」 <A href="https://go.microsoft.com/fwlink/p/?linkid=306064">https://go.microsoft.com/fwlink/p/?LinkId=306064</A>。



</div>

1.  從 Lync Server 前端伺服器開啟 Lync Server 管理命令介面。

2.  執行下列兩個命令：
    
      - `Remove-CsPublicProvider -Identity <identity-name>`
        
        <div>
        

        > [!NOTE]
        > 如果您的環境中還沒有 PIC 提供者，且正在建立新的 PIC 提供者，則不需要執行<STRONG>CsPublicProvider</STRONG> Cmdlet。

        
        </div>
    
      - `New-CsPublicProvider -ProxyFqdn federation.messenger.msn.com -Enabled 1 -Identity Skype  -VerificationLevel 2 -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -IconUrl "https://images.edge.messenger.live.com/Messenger_16x16.png"`
        
        <div>
        

        > [!NOTE]
        > 在 Lync Server 2013 中新增&amp; OFFICE 2013 SP1 中的 CU5 lync 桌面用戶端，這會改善 lync 使用者新增必要的 skype 連絡人至「保密協定」，以找出並將其路由至 Skype （格式為：使用者（contoso .com） @msn .com）。 這些新設定可讓您在 [新增 Skype 連絡人] 對話方塊中的 [新增 Skype 連絡人] 對話方塊中，自動設定位址格式，但如果它不包含 NameDecorationExcludedDomainList 中的網域，則為 NameDecorationRoutingDomain （應設定為 msn.com）。我們目前可以支援 msn.com、live.com、Hotmail.com、outlook.com）。

        
        </div>

3.  您現在可以從 Lync 用戶端選取 [Skype] 作為 PIC 提供者，並透過指定其 Microsoft 帳戶來新增 Skype 用戶端。 此外，已透過其 Microsoft 帳戶合併並登入的 Skype 使用者，可以傳送聯絡人要求給 Lync 使用者。 如需 Microsoft 帳戶的詳細資訊，請參閱[什麼是 microsoft 帳戶？](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account)。 如需將用戶端新增至 Lync 的其他資訊，請參閱[在 Lync Server 2013 中使用 Lync Skype 連線功能做為最終使用者](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)。

4.  如需有關修改託管提供者的詳細資訊，請參閱「建立或編輯託管 SIP [https://go.microsoft.com/fwlink/p/?LinkId=306065](https://go.microsoft.com/fwlink/p/?linkid=306065)聯盟提供者」。

這樣就完成了必須在伺服器上執行的系統管理工作。 您現在已設定 Lync-Skype 連線的連線。

</div>

</div>

<div>

## <a name="additional-resources"></a>其他資源

[在 Lync Server 2013 中以使用者身分使用 Lync-Skype 連線](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)

[Lync Server 2013 的 Lync-Skype 連線佈建指南](lync-server-2013-provisioning-guide-for-lync-skype-connectivity.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

