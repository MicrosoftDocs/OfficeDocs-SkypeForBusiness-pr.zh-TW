---
title: 常見問題集：佈建 Lync Server 以供 Skype 連線
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: 'Frequently Asked Questions: Provisioning Lync Server for Skype connectivity'
ms:assetid: 4d1b2bfc-780b-4b8c-afd5-11c2e59203b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440172(v=OCS.15)
ms:contentKeyID: 57793362
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0fc06cda300945ccf4d7da9424b5615028c2e8f5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974077"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="frequently-asked-questions-provisioning-lync-server-2013-for-skype-connectivity"></a>常見問題集：佈建 Lync Server 以供 Skype 連線

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2019-03-22_

從2019年4月開始，我們會針對透過 pic.lync.com 網站提供 Skype Federation 的客戶停止收集及保留連絡人資訊。 我們正在進行這種變更，以確保 pic.lync.com 置備系統符合 Microsoft 隱私權原則。 
 
此變更生效之後，我們將無法在未決的置備變更上提供電子郵件更新。 PIC 置備變更通常會在輸入後的24-48 小時內完成。 如果您在提交提供要求之後，仍會遇到48小時的 Skype Federation 問題，請與 Microsoft 技術支援人員聯繫，以進一步調查。

> [!IMPORTANT]
> 如此一來，在2019年4月結束後，所有先前輸入的連絡人資訊都會從我們的系統中清除。


**問： Microsoft Lync 與 Skype 之間支援哪些功能？**

**A：** 透過 Skype 現已成為 Microsoft 家庭的一部分，新的可能會開啟，將整合通訊案例延伸至數百萬個使用 Skype 的使用者。 這項組合可讓 Lync 客戶與供應商、客戶和合作夥伴連線並共同作業，依賴 Lync 的豐富程度和 Skype 的範圍。

  - 立即訊息和音訊與視頻通話-Lync 與 Skype 使用者之間的同盟音訊及視頻通話與立即訊息

  - 目前狀態共用-同盟連絡人之間的 Exchange 目前狀態資訊

  - 簡單的管理-設定與控制，可根據貴組織的原則和標準來設定聯盟通訊

**問：我要如何確認我的 Lync 部署與 Skype 連接？**

**A：** 如果您有下列其中一項，就表示您可以使用 Skype 連線的授權：

  - Lync Server （2010或2013）加上 Lync Server 標準版用戶端存取授權（"Cal"; 2010 或2013），適用于您組織中將會連線至 Skype 的使用者和/或裝置。 

  - Lync Online （作為獨立授權或 Office 365 套件的一部分）。不過，此服務（pic.lync.com）只適用于預配 Lync Server 及混合式 Lync Server 和 Lync Online 部署。Lync Online 的 PIC 配是在 Lync Online [控制台] （LOCP）中完成。

**問： Lync 使用者必須執行哪些動作才能連線至 Skype 連絡人？**

**A：** 在啟用網域且組織的 Lync 系統管理員啟用這些功能之後，Lync 使用者就能在 Lync 用戶端的連絡人清單中新增 Skype 連絡人。

**問： Skype 使用者必須執行哪些動作才能連線至 Lync 連絡人？**

**A：** 所有想要連線至 Lync 使用者的 Skype 使用者，都必須有與其 Skype Id 相關聯的 Microsoft 帳戶，然後使用 Microsoft 帳戶登入。您可以在 Skype 用戶端中啟用此功能。

**問：是否仍提供與 Windows Live 的同盟？**

**A：** 從2012年10月起，Microsoft 已開始協助 Windows Live Messenger （WLM）使用者移至 Skype、途中最終停用 WLM。只要 WLM 在市場中，Lync 就會繼續支援與 WLM 的同盟，但不允許其他的 Windows Live domain 啟動。WLM 使用者的移動是由 Mac 版 Skype 6.0 和 Windows （2012年10月25日發行）啟用，這可讓您以 Microsoft 帳戶登入（亦即與 WLM 相同的認證）。 只要登入 Skype，WLM 好友清單就會自動填入 Skype，而且使用者可以利用 Skype 的擴充通訊功能，例如呼叫市話和手機、螢幕共用、群組視頻通話，以及支援寬螢幕各種不同的裝置。此外，WLM 使用者的 [同盟 Lync 連絡人] 會依照連絡人清單中的其他人，然後立即提供這些連絡人的 skype 和 Lync 之間的 IM。 Lync 客戶不需要執行任何動作，即可啟用這項服務的連續性。

**問：是否仍提供 Yahoo\!或 AOL 的同盟？**

**A：** 不。 使用 Yahoo 的同盟\! 而且 AOL 已從 Yahoo 提供支援\! 和 AOL。兩個 Yahoo\! 而且 AOL，服務于2014年6月30日結束。 

**問：您可以先試用 Skype 連線，然後再購買 Lync 嗎？**

**A：** 在試用版中不會提供 Skype 連線。 您可以隨時註冊要測試的 Lync 客戶，而不需試用版。

**問：需要哪些資訊才能進行預配？**

**A：** 若要在合格的授權下提交置備要求，您需要下列各項：

  - Microsoft 合約號碼：
    
      - Microsoft 大量授權支援： Microsoft 大量授權協定編號
    
      - Microsoft 合作夥伴網路： Headquarter 合作夥伴識別碼
    
      - 服務提供者授權協定：初始註冊號碼
    
      - 高容量服務：產品註冊號碼

  - 存取邊緣服務的完整功能變數名稱（Fqdn）。
    
      - 至少需要一個存取邊緣服務的 FQDN。
    
      - 如果您的組織有多台伺服器執行存取邊緣服務，請為每個額外的存取邊緣服務指定 Fqdn。 重要：如果您先前已指定存取邊緣服務的 FQDN，且想要變更它，可能需要幾天的時間來完成變更，並可能導致服務中斷。 若要防止服務中斷，建議您維護先前指定的存取邊緣服務 FQDN。

  - 會話初始通訊協定（SIP）網域。 這是使用者目前用於立即訊息的 SIP URI 網域尾碼。 如果您的組織有一個以上的 SIP 網域，請為用於立即訊息的每個網域指定網域尾碼。 例如，針對 user1@contoso.com，請指定 SIP 網域的 contoso.com;若是 user1@example.fabrikam.com，請將 example.fabrikam.com 指定為 SIP 網域。
    
    <div>
    

    > [!NOTE]
    > 僅指定 SIP 網域的網域尾碼。 請勿為 SIP 網域指定任何 Fqdn，包括存取邊緣服務的 FQDN。

    
    </div>

  - 連絡人資訊。 針對您指定的每個 SIP 網域，指定系統管理員的電子郵件地址。

**問：如何在分割網域案例中啟用 Lync Skype 連線功能？**

**A：** 如果您有 Lync Online 2013 和 Lync Server 內部部署分割網域案例（在線上和內部部署中使用相同的 SIP 網域的使用者），請依照下列循序執行下列兩個步驟，以啟用 Lync Skype 連線能力

1.  根據 PIC 提供指南中的說明，設定內部部署 Lync-Skype 連線能力。

2.  等到您看到您的網域已由 Microsoft 提供確認之後，再進行確認。

3.  在您看到確認之後，請使用 Lync 系統管理中心來開啟 [外部通訊]。 如需詳細資訊，請參閱[http://office.microsoft.com/en-us/support/configure-external-communications-HA102817865.aspx?CTT=5\&origin=HA102817356](http://office.microsoft.com/en-us/support/configure-external-communications-ha102817865.aspx?ctt=5%26origin=ha102817356)

這個順序非常重要。您必須先設定內部部署連線，才能在 Lync Online 中啟用通訊。 如果是相反的順序，則在內部部署中<https://pic.lync.com>輸入的資訊將不會繼續進行。 如果您已將 Lync Online 設定為與此網域進行外部通訊，您必須先將您的內部部署資訊<https://pic.lync.com>輸入，然後開啟 Lync Online 的外部通訊，然後再重新開始。

**問：我可以為 Skype 連線提供多個存取邊緣服務 Fqdn 嗎？**

**A：** 您只能為一或多個網域提供一個存取邊緣 FQDN。 如果有不同的網域，您可以為每個要求提供多個存取邊緣 Fqdn （最多10個）。

**問：我可以取得您針對組織要求提供所找到的 Microsoft 帳戶電子郵件地址清單嗎？**

**A：** 不。 這些位址被視為個人辨識資訊，而且不會被共用。

**問：我要如何新增 ID 包含 Windows Live 不支援之網域的 Windows Live Messenger 連絡人？**

**A：** 如果您要新增包含非 Windows live 網域之帳戶或 ID 的 Windows live Messenger 使用者，請以下列格式\<輸入位址： [使用者名稱\>] （\<功能變數名稱\>） @msn .com]，其中\<domain name\>是使用者電子郵件地址中的功能變數名稱。 例如，如果您想要新增 ted@contoso.com，您可以使用下列格式：李小明（contoso） @msn .com。 如需 Windows Live 所管理網域的清單，請參閱在「安裝 Live 通訊伺服器 Service Pack 1 後，在公用立即訊息中發生的已知問題」的 [支援的網域http://support.microsoft.com/?kbid=897567] 區段。

**問：置備程式需要多少時間？**

**A：** 預配可能需要長達30天的時間。

**問：我要如何在完成調配時知道什麼？**

**A：** 當提供完成時，Microsoft 會傳送電子郵件通知。

**問：我要如何更新我提交的設定或連絡人詳細資料？**

**A：** 您可以在完成調配之後，在您用來要求提供的相同網站上更新您的資訊。 輸入您的協定編號，然後按一下 [更新服務]。

</div>

<span> </span>

</div>

</div>

</div>

