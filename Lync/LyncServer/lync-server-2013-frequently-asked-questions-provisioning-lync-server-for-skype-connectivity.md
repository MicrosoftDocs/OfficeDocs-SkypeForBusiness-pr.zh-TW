---
title: 常見問題集： 佈建 Lync Server 的 Skype 連線
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
ms.openlocfilehash: 718dda9966b79ca75f64df115dc9a6ba30d15619
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136991"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="frequently-asked-questions-provisioning-lync-server-2013-for-skype-connectivity"></a>常見問題： 佈建 Lync Server 2013 的 Skype 連線

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2019年-03-22_

從開始年 4 月 2019年中，我們將會停止集合並保留透過 pic.lync.com 網站佈建 Skype 同盟的客戶的連絡資訊。 這項變更是在進行以確保佈建系統 pic.lync.com 遵守 Microsoft 隱私權原則。 
 
一旦這項變更即可，我們將不再能夠提供電子郵件更新擱置中佈建的變更。 PIC 佈建變更通常後所輸入的 24 到 48 小時內完成。 如果您仍會發生 Skype 同盟問題 48 小時後提交佈建的要求，請洽詢 Microsoft 技術支援，以進一步調查。

> [!IMPORTANT]
> 這項變更的一部分，所有先前所輸入的連絡資訊都將予以從我們的系統 2019 年 4 月日結束。


**問： 何種功能支援 Microsoft Lync 和 Skype 之間？**

**答：** 與 Skype 立即組件中的 Microsoft 系列，新的可能性開啟擴充到數百個數百萬的人員使用 Skype 的整合的通訊案例。 此組合會讓 Lync 客戶連線，並與供應商、 客戶和合作夥伴，信賴憑證者的 Lync 豐富性和 Skype] 的範圍上共同作業。

  - 立即訊息和音訊和視訊通話 — 同盟音訊和視訊通話和立即訊息之間 Lync 與 Skype 使用者

  - 平台服務共用 — Exchange 之間同盟連絡人的目前狀態資訊

  - 簡單的系統管理-設定和控制項設定根據貴組織的原則及標準的同盟的通訊

**問： 如何限定與 Skype 連線我 Lync 部署？**

**答：** 您已授權的 Skype 連線如果您有下列一項：

  - Lync Server （2010年或 2013年） 再加上 Lync Server Standard 用戶端存取授權 （「 Cal 」; 2010年或 2013年） 的使用者及/或將連線到 Skype 您組織中的裝置。 

  - Lync Online （作為獨立授權或 Office 365 套件的一部分）。不過，這項服務 (pic.lync.com) 是僅適用於佈建 Lync Server 與混合式 Lync Server 和 Lync Online 部署。Lync Online PIC 佈建完成在 Lync Online 控制項] 面板 (LOCP)。

**問： 必須 Lync 使用者怎麼做以連線至 Skype 連絡人？**

**答：** 啟動網域且由組織的 Lync 管理員已啟用功能之後，Lync 使用者可以將 Skype 連絡人新增至他們的連絡人清單中的 Lync 用戶端。

**問： 必須用 Skype 使用者怎麼做以連線至 Lync 連絡人？**

**答：** 想要連線至 Lync 使用者的所有 Skype 使用者必須都擁有相關聯 Skype 識別碼與使用 Microsoft 帳戶登入 Microsoft 帳戶。若要啟用 Skype 用戶端內。

**問： 是否同盟與 Windows Live 仍然可以使用？**

**答：** 開始在 2012 年 10 月日，Microsoft 已啟動協助 Windows Live Messenger (WLM) 的使用者移至 Skype，途中最終淘汰 WLM。Lync 仍會繼續只要 WLM 市場，但是卻沒有其他 Windows Live 網域啟用仍支援與 WLM 同盟。WLM 使用者的移動會啟用商務用 Skype 6.0 Mac 和 Windows （發行 2012 年 10 月 25 日） 可讓登入 Microsoft 帳戶 （亦即，為 WLM 的相同認證）。 只要登入 Skype，WLM 朋友清單會自動填入到 Skype，且使用者可以利用 Skype 的展開的通訊功能，例如呼叫 landlines 和 mobiles、 螢幕共用之後，群組視訊通話，並支援整個各種不同的裝置。此外，WLM 使用者的同盟的 Lync 連絡人請依照下列轉換成 Skype 與他們的朋友清單的其餘部分，Skype 和 Lync for 這些連絡人之間的 IM 立即將提供使用。 Lync 客戶不需要執行任何動作來啟用此持續性的服務。

**問： 是否與 Yahoo 同盟\!或 AOL 仍然可以使用？**

**答：**[否]。 Yahoo 與同盟\! AOL 視 Yahoo 的支援，且\! 和 AOL。針對這兩個 Yahoo\! 和 AOL，已於 2014 年 6 月 30 日結束的服務。 

**問： 我可以試用版 Skype 連線之前購買 Lync 嗎？**

**答：** Skype 連線不是提供試用版為基礎。 試用版，取代合格授權的 Lync 客戶所建議只註冊服務來測試。

**問： 何種資訊才佈建？**

**答：** 若要提交下合格授權的佈建要求，您需要下列項目：

  - Microsoft 合約號碼：
    
      - Microsoft 大量授權支援： Microsoft 大量授權合約號碼
    
      - Microsoft Partner Network: Headquarter 協力程式識別碼
    
      - 服務提供者授權合約： 初始註冊號碼
    
      - 高磁碟區服務： 產品註冊號碼

  - 完整的 Access Edge service 的網域名稱 (Fqdn)。
    
      - 需要至少一個 Access Edge service 的 FQDN。
    
      - 如果您的組織有多個執行 Access Edge service 的伺服器，指定每個額外的 Access Edge service 的 Fqdn。 重要： 如果您先前指定的 Access Edge service 的 FQDN，而且想要將它變更，佈建的變更可能需要數天才能完成而可能導致服務中斷。 若要避免服務中斷，我們建議您維護的 Access Edge service 先前指定的 FQDN。

  - 工作階段初始通訊協定 (SIP) 網域。 這是使用者目前正在使用的立即訊息的 SIP URI 的網域尾碼。 如果您的組織有多個 SIP 網域，指定用於立即訊息的每個網域的網域尾碼。 例如，對於 user1@contoso.com，指定 [SIP 網域; contoso.com針對 user1@example.fabrikam.com，指定 example.fabrikam.com 和的 SIP 網域。
    
    <div>
    

    > [!NOTE]
    > 指定只的 SIP 網域的網域尾碼。 未指定任何 Fqdn] 中，包括 [Access Edge service] 個 SIP 網域的 FQDN。

    
    </div>

  - 連絡人資訊。 指定之管理員的您指定的每個 SIP 網域的電子郵件地址。

**問： 如何啟用分割網域案例中的 Lync Skype 連線？**

**答：** 如果您有 Lync Online 2013 及 Lync Server 內部部署分割網域案例 （與使用者在線上和內部部署使用相同的 SIP 網域） 依照下列順序這兩個步驟啟用 Lync Skype 連線

1.  設定內部部署 Lync Skype 連線 PIC 佈建指南中所述。

2.  請稍候，直到您看到您的網域具有已由 Microsoft 所提供的確認。

3.  您會看到確認之後，請開啟 「 外部通訊 」 使用 Lync 系統管理中心。 如需詳細資訊，請參閱[http://office.microsoft.com/support/configure-external-communications-HA102817865.aspx?CTT=5\&origin=HA102817356](http://office.microsoft.com/support/configure-external-communications-ha102817865.aspx?ctt=5%26origin=ha102817356)

這個順序很重要。啟用 Lync Online 中的通訊之前，您必須設定內部部署連線能力。 如果順序為相反，輸入內部部署中的資訊<https://pic.lync.com>不會通過。 如果您已經有此網域與外部通訊設定好 Lync Online，您必須將它關閉，等候 24 小時、，然後再次啟動，第一次輸入您的內部部署資訊位於<https://pic.lync.com>，然後開啟 [Lync online 的外部通訊。

**問： 可以佈建多個 Access Edge 服務 Fqdn 的 Skype 連線？**

**答：** 您可以佈建一或多個網域只能有一個的 access 的 edge FQDN。 如果他們有不同的網域，您可以佈建多個 access edge Fqdn，最多為每個要求，10。

**問： 可以取得您找到組織要求佈建的 Microsoft 帳戶電子郵件地址的清單？**

**答：**[否]。 這些地址會被視為個人識別資訊，並不會共用。

**問： 如何新增 Windows Live Messenger 連絡人已包含網域以外支援的 Windows Live ID？**

**答：** 如果您要新增帳戶或識別碼與 Windows Live Messenger 使用者與非 Windows Live 網域，輸入地址格式如下：\<使用者名\>(\<網域名稱\>) @msn.com，其中\<網域名稱\>是在使用者的電子郵件地址的網域名稱。 例如，如果您想要新增 ted@contoso.com，您可以使用下列格式： ted (contoso.com) @msn.com。 由 Windows Live 管理的網域的清單，請參閱支援的網域] 區段中的 「 已知問題公用立即訊息與該 Occur 之後安裝 Live Communications Server Service Pack 1 」，在https://support.microsoft.com/?kbid=897567。

**問： 如何佈建程序需要花費時間？**

**答：** 佈建可能需要最多 30 天。

**問： 如何將會知道完成佈建時？**

**答：** Microsoft 會傳送電子郵件通知佈建時已完成。

**問： 如何更新組態或連絡我送出的詳細資訊嗎？**

**答：** 您可以更新您在相同的網站，您用來要求佈建，佈建完成後的資訊。 輸入您合約數字，然後按一下 [更新服務。

</div>

<span> </span>

</div>

</div>

</div>

