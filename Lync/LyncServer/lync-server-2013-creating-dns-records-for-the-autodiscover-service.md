---
title: Lync Server 2013： 建立 DNS 記錄的自動探索服務
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating DNS records for the Autodiscover Service
ms:assetid: 3756ffe4-c6b1-492d-850e-42a832e06567
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690010(v=OCS.15)
ms:contentKeyID: 48183823
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a3c9e3b3aaecef519a2fbc23d5955a5be4fa0d0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048644"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-dns-records-for-the-autodiscover-service-in-lync-server-2013"></a>Lync Server 2013 中的自動探索服務建立 DNS 記錄

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2014年-06-20 個_

Lync 行動使用者必須先啟用自動探索，以及的一部分，包括建立一些網域名稱系統 (DNS) 記錄。 根據您的需求，您需要下列各項：

  - 內部 DNS 記錄，以支援行動裝置正在從網際網路連接貴組織的網路內的使用者。

  - 外部或公用 DNS 記錄，以支援從網際網路連接的行動使用者

為什麼兩者嗎？ 您必須建立內部 DNS 記錄和外部 DNS 記錄每個 SIP 網域。

您建立的 DNS 記錄可以是其中一個 A （主機），記錄或 CNAME 記錄。 為了協助您取出，我們將逐步解說如何建立這些內部和外部 DNS 記錄下方。 如果您需要執行一些進一步閱讀行動使用者的 DNS 需求，您可以查看[Lync Server 2013 中的行動的技術需求](lync-server-2013-technical-requirements-for-mobility.md)。

<div>

## <a name="creating-an-internal-dns-cname-record"></a>建立內部 DNS CNAME 記錄

1.  若要讓內部 DNS 記錄，您需要登入是 Domain Admins 群組的成員或 DnsAdmins 群組成員的網域帳戶與您網路中 DNS 伺服器。

2.  開啟 DNS 系統管理嵌入式管理單元：依序按一下 [開始]****、[系統管理工具]**** 和 [DNS]****。

3.  在 [DNS 伺服器的主控台樹狀目錄中，依序展開 [**正向對應區域**安裝 Lync Server 2013 Director 集區與前端集區的 Active Directory 網域。 (例如 contoso.local)。

4.  檢查，請參閱是否 (對於 IPv6 為 AAAA) 記錄存在，您的 Director 集區，針對內部 DNS 記錄的主機，主機 A 記錄應該存在於內部 Web 服務完整的網域名稱 (FQDN) Director 集區 (例如 lyncwebdir01.contoso.local)。 如果它不是在這裡，您不使用 Director 集區]，而您將需要您的前端集區或甚至是在單一伺服器 FQDN] 中，使用 FQDN，如果這是您的設定。

5.  請記住，，檢查並查看是否 (對於 IPv6 為 AAAA) 記錄存在，您的前端集區，針對內部 DNS 記錄的主機，主機 A （或 AAAA） 記錄應存在於您的前端集區的內部 Web 服務 fqdn （例如lyncwebpool01.contoso.local)。 如果沒有，您需要記前端伺服器或 Standard Edition server 的 FQDN。

6.  一旦您知道哪些主機 A （或 AAAA） 的記錄存在，您的 DNS 伺服器的主控台樹狀目錄中展開 SIP 網域 (例如，contoso.com) 的 [**正向對應區域**。

7.  用滑鼠右鍵按一下 SIP 網域名稱，然後按一下 [新增別名 (CNAME)]****。

8.  在 [**別名名稱**] 中，輸入 lyncdiscoverinternal 作為內部自動探索服務 URL 的主機名稱。

9.  在**完整目標主機的網域名稱 (FQDN)**，輸入或瀏覽至您的 Director 集區 (例如 lyncwebdir01.contoso.local) 的內部 Web 服務 FQDN，然後按一下 **[確定]**。

10. 您必須在您支援 Lync Server 2013 環境中的每個 SIP 網域的正向對應區域中建立新的自動探索 CNAME 記錄。

</div>

<div>

## <a name="creating-an-external-dns-cname-record"></a>建立外部 DNS CNAME 記錄

1.  若要建立外部 DNS CNAME 記錄，您即將需要連線至公用 DNS 提供者，並依照我們的步驟。 我們無法說明完全其中您即將 DNS 提供者的環境中可能有不同的方式，管理您的外部 DNS，但是我們希望這些步驟協助。

2.  登入外部 DNS 提供者可以在該環境中建立 DNS 記錄的帳戶。

3.  您應該已建立此環境的 SIP 網域。 依序展開 [**正向對應區域**此 SIP 網域，或否則根據所使用的外部 DNS 介面選取它。

4.  您應該已如 Director 集區 （例如 lyncwebexdir01.contoso.com)，請參閱主機 A (對於 IPv6 為 AAAA) 記錄，因此確認它有。 如果不是，那麼您可能不使用 Director 集區。 如果是這種情況，您需要使用的 FQDN，您前端集區，或如果您正在執行此動作的單一伺服器，您的前端伺服器或 Standard Edition server。

5.  您也需要確認是否您不有任何前端集區的主機 A (對於 IPv6 為 AAAA) 記錄存在您外部 Web 服務完整完整網域名稱 (FQDN) （例如 lyncwebextpool01.contoso.com)、 前端集區或單一伺服器 fqdn 的 FQDN。 上一個步驟所述，您將需要這個下方如果您不需要 Director 集區。

6.  現在，在外部 DNS 提供者的適當格式，選擇 [建立**新別名 (CNAME)** （可能是功能表選項或連結，視 DNS 提供者的格式） 中的選項。

7.  為使用內部 DNS 中，您應該輸入 lyncdiscover 作為外部自動探索服務 URL 的主機名稱時，則應該是某種形式的**別名名稱**] 文字方塊。

8.  也應某種形式的**完整網域名稱 (FQDN) 目標主機的**文字] 方塊中，以下其中您將為您的 Director 集區 (例如，lyncwebexdir01.contoso.com) 輸入外部 Web 服務 FQDN 然後按一下 [確定] 或接受此項目建立外部 DNS 中採取動作。 如上所述在步驟 4 中，如果您沒有 Director 集區]，您需要使用前端集區的 FQDN 或單一伺服器 FQDN 您已設定好，視需要。

9.  您需要在 Lync 2013 環境中支援的每個 SIP 網域的正向對應區域中進行新的自動探索 CNAME 記錄。

</div>

<div>

## <a name="creating-an-internal-dns-a-record"></a>建立內部 DNS A 記錄

1.  若要讓內部 DNS 記錄，登入是 Domain Admins 群組的成員或 DnsAdmins 群組成員的網域帳戶與您網路的 DNS 伺服器。

2.  開啟 DNS 系統管理嵌入式管理單元：依序按一下 [開始]****、[系統管理工具]**** 和 [DNS]****。

3.  針對內部 DNS 記錄，DNS 伺服器的主控台樹狀目錄中展開 Active Directory 網域 (例如 contoso.local) 安裝 Lync Server 2013 Director 集區與前端集區的 [**正向對應區域**。

4.  檢查，請參閱是否 (對於 IPv6 為 AAAA) 記錄存在，您的 Director 集區，針對內部 DNS 記錄的主機，主機 A 記錄應該存在於內部 Web 服務完整的網域名稱 (FQDN) Director 集區 (例如 lyncwebdir01.contoso.local)。 如果它不是在這裡，您不使用 Director 集區，而您將需要使用 IP 位址前端集區或甚至是單一伺服器的 IP 位址，如果這是您的設定。

5.  請記住，，檢查並查看是否 (對於 IPv6 為 AAAA) 記錄存在，您的前端集區，針對內部 DNS 記錄的主機，主機 A （或 AAAA） 記錄應存在於您的前端集區的內部 Web 服務 fqdn （例如lyncwebpool01.contoso.local)。 如果沒有，您需要記前端伺服器或 Standard Edition 伺服器的 IP 位址。

6.  一旦您知道哪些主機 A （或 AAAA） 的記錄存在，您的 DNS 伺服器的主控台樹狀目錄中展開 SIP 網域 (例如，contoso.com) 的 [**正向對應區域**。

7.  用滑鼠右鍵按一下 SIP 網域名稱，然後按一下 [新增主機 (A 或 AAAA)]****。

8.  在 [**名稱**] 中，輸入 lyncdiscoverinternal 作為內部自動探索服務 URL 的主機名稱。

9.  在 [ **IP 位址**] 中，輸入 Director 的內部 Web 服務 IP 位址 （或者，如果您使用負載平衡器，請輸入虛擬 IP (VIP) Director 負載平衡器）。 如如果您不使用 Director，與上述步驟 4 中所述，您可能需要輸入前端伺服器或 Standard Edition server 的 IP 位址，或如果您使用負載平衡器中，輸入前端集區負載平衡器的 VIP。

10. 按一下 [新增主機]****，然後按一下 [確定]****。

11. 若要建立其他的 A 或 AAAA 記錄，重複步驟 8 到 10，請記住，您需要建立新的自動探索 A 或 AAAA 記錄中有支援 Lync Server 2013 環境中的每個 SIP 網域的正向對應區域。

12. 完成建立 A (對於 IPv6 為 AAAA) 記錄時，按一下 [完成]****。

</div>

<div>

## <a name="creating-an-external-dns-a-record"></a>建立外部 DNS A 記錄

1.  若要建立外部 DNS 記錄，連線至公用 DNS 提供者，並依照我們的步驟。 我們無法說明完全其中您即將 DNS 提供者的環境中可能有不同的方式，管理您的外部 DNS，但是我們希望這些步驟協助。

2.  您需要的帳戶，可以在該環境中建立 DNS 記錄以登入。

3.  針對外部 DNS 記錄，在 DNS 伺服器的主控台樹狀目錄中，展開 SIP 網域 (例如 contoso.com) 的 [正向對應區域]****。 針對外部 DNS 記錄，在 DNS 伺服器的主控台樹狀目錄中，展開 SIP 網域 (例如 contoso.com) 的 [正向對應區域]****。

4.  您應該已如 Director 集區 （例如 lyncwebexdir01.contoso.com)，請參閱主機 A (對於 IPv6 為 AAAA) 記錄，因此請先確認有且 IP 位址是。 如果不是，那麼您可能不使用 Director 集區。 如果是這種情況，您需要使用 IP 位址的您前端集區，或如果您正在執行此動作的單一伺服器，您的前端伺服器或 Standard Edition server。 請記住，您的伺服器也可能背後的負載平衡器，或使用反向 proxy。 記下的 IP 位址以及遵循下列步驟。

5.  您也需要確認主機 A (對於 IPv6 為 AAAA) 記錄存在您外部 Web 服務完整完整網域名稱 (FQDN) （例如 lyncwebextpool01.contoso.com)、 前端集區或單一伺服器 Lync 安裝 IP 位址。 是否您不有任何前端集區。 上一個步驟所述，您將需要這個下方如果您不需要 Director 集區。

6.  現在，在外部 DNS 提供者的適當格式，選擇 [建立**新的主機 A 或 AAAA** （可能是功能表選項或連結，視 DNS 提供者的格式） 中的選項。

7.  應該輸入的**名稱**、 輸入 lyncdiscover 作為外部自動探索服務 URL 的主機名稱的位置。

8.  也應**IP 位址**] 文字方塊中，以下是您要在其中輸入的 IP 您的 Director 集區 (例如，lyncwebexdir01.contoso.com) 或可能是 IP 集區的負載平衡器 （或反向 proxy IP 通往相同） 然後按一下 [確定] 或接受此項目建立外部 DNS 中採取動作。 如上所述在步驟 4 中，如果您沒有 Director 集區]，您需要使用的前端集區 IP 位址或您已設定好，單一伺服器 IP 位址為適當。

9.  您需要在 Lync 2013 環境中支援的每個 SIP 網域的正向對應區域中進行新的自動探索 A 或 AAAA 記錄。

</div>

</div>

<span> </span>

</div>

</div>

</div>

