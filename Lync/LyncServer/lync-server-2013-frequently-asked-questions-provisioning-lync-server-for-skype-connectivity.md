---
title: 常見問題：布建 Lync Server 以進行 Skype 連線
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Frequently Asked Questions: Provisioning Lync Server for Skype connectivity'
ms:assetid: 4d1b2bfc-780b-4b8c-afd5-11c2e59203b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440172(v=OCS.15)
ms:contentKeyID: 57793362
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0315104e4bbbd2d8741d5bc011455be2d28191dc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500810"
---
# <a name="frequently-asked-questions-provisioning-lync-server-2013-for-skype-connectivity"></a>常見問題：布建 Lync Server 2013 for Skype connectivity

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2019-03-22_

從2019年4月開始，我們將停止透過 pic.lync.com 網站為 Skype 同盟布建之客戶的連絡人資訊的收集和保留。 進行此變更是為了確保 pic.lync.com 布建系統遵守 Microsoft 隱私權原則。 
 
這種變更生效後，我們將無法再在暫止的布建變更上提供電子郵件更新。 PIC 布建變更通常會在進入之後的24-48 小時內完成。 如果您在提交布建要求之後仍會出現48小時的 Skype 同盟問題，請與 Microsoft 技術支援人員接洽，以進一步調查。

> [!IMPORTANT]
> 做為此變更的一部分，所有先前輸入的連絡人資訊都會在2019年4月結束時從系統中清除。


**問： Microsoft Lync 與 Skype 之間支援的功能為何？**

**A：** 使用 Skype now Microsoft 系列的一部分，新可能會開啟將整合通訊案例擴充至使用 Skype 的數百個人。 這項結合可讓 Lync 客戶與供應商、客戶及合作夥伴進行連線及共同作業，以依賴 Lync 的豐富功能和 Skype 的範圍。

  - 立即訊息和音訊和影片通話-Lync 與 Skype 使用者之間的同盟音訊和影片通話和立即訊息

  - 目前狀態共用-同盟連絡人之間的 Exchange 顯示狀態資訊

  - 簡單的管理-設定和控制，以根據您組織的原則和標準設定同盟通訊

**問：如何才能使用 Skype 進行 Lync 部署的資格？**

**A：** 如果您有下列其中一項，您就可以使用 Skype connectivity 授權：

  - Lync Server (2010 或 2013) 加上 Lync Server Standard Client Access 授權 ( "Cal";2010或 2013) ，適用于您組織中將會連線到 Skype 的使用者和/或裝置。 

  - Lync Online (為獨立授權或 Office 365 套件的一部分) 。不過，此服務 (pic.lync.com) 僅用於布建 Lync Server 和混合 Lync Server 和 Lync Online 部署。Lync Online PIC 布建是在 Lync Online 控制台中執行 (LOCP) 。

**問： Lync 使用者必須執行哪些動作才能連線到 Skype 連絡人？**

**A：** 在啟用網域且組織的 Lync 系統管理員啟用功能之後，Lync 使用者便可在 Lync 用戶端中將 Skype 連絡人新增至其連絡人清單中。

**問： Skype 使用者必須執行哪些動作才能連接至 Lync 連絡人？**

**A：** 所有想要連接至 Lync 使用者的 Skype 使用者，都必須具有與其 Skype IDs 相關聯的 Microsoft 帳戶，並使用 Microsoft 帳戶登入。您可以在 Skype 用戶端內啟用此功能。

**Q：是否仍可與 Windows Live 進行同盟？**

**A：** 從2012年10月開始，Microsoft 開始協助 Windows Live Messenger (WLM) 使用者移至 Skype，途中最後淘汰 WLM。只要 WLM 位於市場，Lync 便會繼續支援與 WLM 的同盟，但不允許額外的 Windows Live domain 啟用。WLM 使用者的移動是由 Skype 6.0 for Mac 和 Windows 2012 (啟用。) 這允許以 Microsoft 帳戶登入， (也就是與 WLM) 相同的認證。 登入 Skype 後，WLM 好友清單便會自動填入 Skype，而且使用者可以利用 Skype 已擴充的通訊功能（例如呼叫 landlines 和 mobiles、螢幕共用、群組影片通話，以及支援多種裝置）。此外，WLM 使用者的同盟 Lync 連絡人會依照其他人的連絡人清單的方式轉換為 Skype，而且可以立即使用 Skype 和 Lync 之間的 IM。 Lync 客戶不需要執行任何動作，即可啟用這項服務的連續性。

**Q：是否 \! 仍可使用 Yahoo 或 AOL 進行同盟？**

**A：** 不。 使用 Yahoo 的同盟\! 和 AOL 從 Yahoo 提供支援\! 和 AOL。這兩個 Yahoo\! 和 AOL，此服務于2014年6月30日結束。 

**問：我可以在購買 Lync 之前試用 Skype 連線嗎？**

**A：** 不會在試用版上提供 Skype 連線。 若要取代試用版，可鼓勵具有合格授權的 Lync 客戶直接註冊服務以進行測試。

**問：布建需要哪些資訊？**

**A：** 若要在合格的授權下提交布建要求，您需要下列各項：

  - Microsoft 合約號碼：
    
      - Microsoft 大量授權支援： Microsoft 大量授權合約編號
    
      - Microsoft 合作夥伴網路： Headquarter 合作夥伴識別碼
    
      - 服務提供者授權合約：初始註冊號碼
    
      - 大量服務：產品註冊號碼

  - Access Edge service 的完整功能變數名稱 (Fqdn) 。
    
      - 至少需要一個 Access Edge service 的 FQDN。
    
      - 如果您的組織有多部執行 Access Edge service 的伺服器，請為每一個額外的 Access Edge service 指定 Fqdn。 重要事項：如果您先前已指定 Access Edge service 的 FQDN，而且想變更它，則變更的布建可能需要數天才能完成，而且可能會造成服務中斷。 為了避免服務中斷，建議您維護先前指定的 Access Edge service FQDN。

  - 會話初始通訊協定 () 網域 (s) 的 SIP。 這是使用者目前用於立即訊息的 SIP URI 的網域尾碼。 如果您的組織有一個以上的 SIP 網域，請為用於立即訊息的每個網域指定網域尾碼。 例如，若為 user1@contoso.com，請指定 SIP 網域的 contoso.com;若為 user1@example.fabrikam.com，請將 example.fabrikam.com 指定為 SIP 網域。
    
    <div>
    

    > [!NOTE]
    > 僅指定 SIP 網域的網域尾碼。 請勿為 SIP 網域指定任何 Fqdn （包括 Access Edge service 的 FQDN）。

    
    </div>

  - 連絡人資訊。 針對您指定的每個 SIP 網域，指定其系統管理員的電子郵件地址。

**問：如何在分割網域案例中啟用 Lync-Skype 連線功能？**

**A：** 如果您有 Lync Online 2013 和 Lync Server 內部部署分割網域案例 (與使用相同 SIP 網域的線上和內部部署使用者) ，請依下列循序執行這兩個步驟以啟用 Lync-Skype 連線能力。

1.  如 PIC 布建指南所述，設定內部部署 Lync-Skype 連線。

2.  請稍候，直到您看到您的網域已由 Microsoft 提供的確認。

3.  在您看到確認之後，請使用 Lync 系統管理中心開啟「外部通訊」。 如需詳細資訊，請參閱 [https://office.microsoft.com/support/configure-external-communications-HA102817865.aspx?CTT=5\&origin=HA102817356](https://office.microsoft.com/support/configure-external-communications-ha102817865.aspx?ctt=5%26origin=ha102817356)

這種順序很重要。在 Lync Online 中啟用通訊之前，您必須先設定內部部署連線能力。 若反轉順序，輸入內部部署的資訊 <https://pic.lync.com> 將不會經過。 如果您已經為與此網域的外部通訊設定 Lync Online，您必須將它關閉、等候24小時，然後重新開始，請先在中輸入您的內部部署資訊，然後 <https://pic.lync.com> 開啟 Lync Online 的外部通訊。

**問：我是否可以為 Skype 連線提供多個 Access Edge service Fqdn？**

**A：** 您只能為一或多個網域布建一個存取 edge FQDN。 您可以布建多個存取 edge Fqdn，每個要求最多10個，如果有不同的網域。

**問：我是否可以取得您為組織要求布建所找到的 Microsoft 帳戶電子郵件地址清單？**

**A：** 不。 這些位址被視為個人身分識別資訊，而且不會共用。

**問：如何新增 Windows Live Messenger 連絡人，其識別碼包含 Windows Live 所支援的網域以外的其他網域？**

**A：** 若要使用非 Windows Live 網域來新增具有帳戶或 ID 的 Windows Live Messenger 使用者，請以下列格式輸入該位址： \<user name\> (\<domain name\>) @msn .com，其中 \<domain name\> 是使用者電子郵件地址中的功能變數名稱。 例如，如果您想要新增 ted@contoso.com，您可以使用下列格式：李小明 (contoso.com) @msn .com。 如需 Windows Live 所管理的網域清單，請參閱「支援的網域」區段中的「在您安裝 Live 通訊伺服器 Service Pack 1 後，公用立即訊息所發生的已知問題」 https://support.microsoft.com/?kbid=897567 。

**問：布建過程需要多久時間？**

**A：** 布建可能需要最多30天。

**問：如何在布建完成時知道如何？**

**A：** 當布建完成時，Microsoft 會傳送電子郵件通知。

**問：如何更新我提交的設定或連絡人詳細資料？**

**A：** 您可以在完成布建之後，于您用來要求布建的相同網站上更新您的資訊。 輸入您的合約號碼，然後按一下 [更新服務]。

</div>

<span> </span>

</div>

</div>

</div>
