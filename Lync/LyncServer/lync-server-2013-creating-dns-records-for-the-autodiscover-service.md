---
title: Lync Server 2013：建立自動探索服務的 DNS 記錄
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
ms.openlocfilehash: 928de572305cdbe19f5222f34e6616a8022e37b3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531540"
---
# <a name="creating-dns-records-for-the-autodiscover-service-in-lync-server-2013"></a>在 Lync Server 2013 中建立自動探索服務的 DNS 記錄

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-06-20_

您的 Lync Mobile 使用者將需要您啟用自動探索功能，其中包含建立某些網域名稱系統 (DNS) 記錄的部分。 視您的需求而定，您需要下列各項：

  - 內部 DNS 記錄，以支援從組織網路內部連線的行動使用者。

  - 支援從網際網路連線之行動使用者的外部或公用 DNS 記錄

為何？ 您必須為每個 SIP 網域建立內部 DNS 記錄和外部 DNS 記錄。

您建立的 DNS 記錄可以是 (主機，也可以是) 記錄或 CNAME 記錄。 為了協助您完成，我們將逐步說明如何建立下列內部和外部 DNS 記錄。 如果您需要進一步閱讀行動使用者的 DNS 需求，您可以 [在 Lync Server 2013 中查看行動的技術需求](lync-server-2013-technical-requirements-for-mobility.md)。

<div>

## <a name="creating-an-internal-dns-cname-record"></a>建立內部 DNS CNAME 記錄

1.  若要建立內部 DNS 記錄，您必須使用 domain Admins 群組成員或 DnsAdmins 群組成員的網域帳戶，登入網路中的 DNS 伺服器。

2.  開啟 DNS 系統管理嵌入式管理單元：依序按一下 [開始]****、[系統管理工具]**** 和 [DNS]****。

3.  在 DNS 伺服器的主控台樹中，展開您的 Lync Server 2013 Director 集區和前端集區之 Active Directory 網域的 [ **正向對應區域** ]。  (例如，contoso) 本機。

4.  檢查並查看主機 A (AAAA for a IPv6) 記錄是否存在內部 DNS 記錄的 Director 集區。主機 A 記錄應該存在於 Director 集區的內部 Web 服務完整功能變數名稱 (FQDN) 例如，lyncwebdir01.contoso.local (。 如果不在這裡，您可能不會使用 Director 集區，您也必須使用前端集區的 FQDN，或甚至是單一伺服器 FQDN （如果您設定的話）。

5.  請注意，請檢查並查看主機 A () IPv6 AAAA 是否存在用於內部 DNS 記錄的前端集區。主機 A (或 AAAA) 記錄應該存在於前端集區的內部 Web 服務 FQDN (例如，lyncwebpool01.contoso.local 的) 。 如果不是，您需要記下前端伺服器或 Standard Edition server 的 FQDN。

6.  知道存在 (或 AAAA) 記錄的主機之後，在 DNS 伺服器的主控台樹中，展開 SIP 網域的 [ **正向對應區域** ] (例如，contoso.com) 。

7.  用滑鼠右鍵按一下 SIP 網域名稱，然後按一下 [新增別名 (CNAME)]****。

8.  在 [ **別名**] 中，輸入 lyncdiscoverinternal 做為內部自動探索服務 URL 的主機名稱。

9.  在 [ **完整功能變數名稱 (目標主機的 FQDN) **] 中，輸入或流覽至 Director 集區的內部 WEB 服務 FQDN (例如，lyncwebdir01.contoso.local) ，然後按一下 **[確定]**。

10. 您必須在 Lync Server 2013 環境中所支援的每個 SIP 網域的正向對應區域中建立新的自動探索 CNAME 記錄。

</div>

<div>

## <a name="creating-an-external-dns-cname-record"></a>建立外部 DNS CNAME 記錄

1.  若要建立外部 DNS CNAME 記錄，您必須連線至您的公用 DNS 提供者，然後依照我們的步驟進行。 我們無法確切描述您在 DNS 提供者環境中所前往的位置，因為可能會有不同的方式來管理您的外部 DNS，但是我們希望這些步驟有所説明。

2.  使用可在該環境中建立 DNS 記錄的帳戶，登入您的外部 DNS 提供者。

3.  您應該已經為此環境建立 SIP 網域。 展開此 SIP 網域的 **正向對應區域** ，或根據所使用的外部 DNS 介面，加以選取。

4.  您應該會看到主機 A (AAAA IPv6 Director 集區的) 記錄 (例如 lyncwebexdir01.contoso.com) ，所以請確認已存在。 如果不是，則您可能不是使用 Director 集區。 如果是這種情況，您必須使用前端集區的 FQDN，或在您的 Front-End server 或 Standard Edition server 上執行這項操作的單一伺服器。

5.  您也需要確認主機 A IPv6) 記錄的 (AAAA 是否存在於您的外部 Web 服務完整功能變數名稱 (FQDN) 如 lyncwebextpool01.contoso.com (，或您的單一伺服器 FQDN （如果您沒有前端集區）的 FQDN。 如先前的步驟所述，如果您沒有 Director 集區，則需要下列步驟。

6.  現在，在您的外部 DNS 提供者適當的格式中，選擇建立 **新別名 (CNAME) ** (此選項可能是功能表選項或連結，視 DNS 提供者) 格式而定。

7.  您應輸入 lyncdiscover 做為外部自動探索服務 URL 的主機名稱，才能使用一些形式的 **別名名稱** 文字方塊。

8.  在 [目標主機] 文字方塊的 FQDN) 中，也應該會有某種形式的 **完整功能變數名稱 (** ，您可以在這裡輸入您 Director 集區的外部 WEB 服務 FQDN (例如，lyncwebexdir01.contoso.com) 然後按一下 [確定]，或在外部 DNS 中執行任何動作，以接受此專案的建立。 如以上的步驟4所述，如果您沒有 Director 集區，則需要使用您設定的前端集區 FQDN 或單一伺服器 FQDN （如果適用）。

9.  您必須在 Lync 2013 環境所支援的每個 SIP 網域的正向對應區域中，建立新的自動探索 CNAME 記錄。

</div>

<div>

## <a name="creating-an-internal-dns-a-record"></a>建立內部 DNS A 記錄

1.  若要建立內部 DNS 記錄，請使用 Domain Admins 群組成員的網域帳戶或 DnsAdmins 群組的成員，登入網路中的 DNS 伺服器。

2.  開啟 DNS 系統管理嵌入式管理單元：依序按一下 [開始]****、[系統管理工具]**** 和 [DNS]****。

3.  針對內部 DNS 記錄，在 DNS 伺服器的主控台樹中，展開 Active Directory 網域的 [ **正向對應區域** ] (例如，contoso) 會安裝 Lync Server 2013 Director 集區和前端集區的位置。

4.  檢查並查看主機 A (AAAA for a IPv6) 記錄是否存在內部 DNS 記錄的 Director 集區。主機 A 記錄應該存在於 Director 集區的內部 Web 服務完整功能變數名稱 (FQDN) 例如，lyncwebdir01.contoso.local (。 如果不在這裡，您可能不會使用 Director 集區，您也必須使用前端集區的 IP 位址，或甚至單一伺服器 IP 位址（如果您設定的話）。

5.  請注意，請檢查並查看主機 A () IPv6 AAAA 是否存在用於內部 DNS 記錄的前端集區。主機 A (或 AAAA) 記錄應該存在於前端集區的內部 Web 服務 FQDN (例如，lyncwebpool01.contoso.local 的) 。 如果不是，您需要記下前端伺服器或 Standard Edition server 的 IP 位址。

6.  知道存在 (或 AAAA) 記錄的主機之後，在 DNS 伺服器的主控台樹中，展開 SIP 網域的 [ **正向對應區域** ] (例如，contoso.com) 。

7.  用滑鼠右鍵按一下 SIP 網域名稱，然後按一下 [新增主機 (A 或 AAAA)]****。

8.  在 [ **名稱**] 中，輸入 lyncdiscoverinternal 做為內部自動探索服務 URL 的主機名稱。

9.  在 [ **IP 位址**] 中，輸入 director (的內部 WEB 服務 IP 位址，或者，如果您使用負載平衡器，請輸入 director 負載平衡器) 的虛擬 IP (VIP) 。 如以上步驟4所述，如果您不是使用 Director，您可能需要輸入前端伺服器或 Standard Edition 伺服器的 IP 位址，或者，如果使用負載平衡器，請輸入前端集區負載平衡器的 VIP。

10. 按一下 [新增主機]****，然後按一下 [確定]****。

11. 若要建立額外的 A 或 AAAA 記錄，請重複步驟8到10，請記住，您必須在 Lync Server 2013 環境所支援的每個 SIP 網域的正向對應區域中建立新的自動探索 A 或 AAAA 記錄。

12. 完成建立 A (對於 IPv6 為 AAAA) 記錄時，按一下 [完成]****。

</div>

<div>

## <a name="creating-an-external-dns-a-record"></a>建立外部 DNS A 記錄

1.  若要建立外部 DNS 記錄，請連接到您的公用 DNS 提供者，然後依照我們的步驟進行。 我們無法確切描述您在 DNS 提供者環境中所前往的位置，因為可能會有不同的方式來管理您的外部 DNS，但是我們希望這些步驟有所説明。

2.  您必須以帳戶的身分登入，才能在該環境中建立 DNS 記錄。

3.  針對外部 DNS 記錄，在 DNS 伺服器的主控台樹狀目錄中，展開 SIP 網域 (例如 contoso.com) 的 [正向對應區域]****。 針對外部 DNS 記錄，在 DNS 伺服器的主控台樹狀目錄中，展開 SIP 網域 (例如 contoso.com) 的 [正向對應區域]****。

4.  您應該會看到 a a a a a a a a a a a a (AAAA IPv6 for a a a a a a a A a a a a A A a a A a a A a a a a a a a a) )  (record 如果不是，則您可能不是使用 Director 集區。 如果是這種情況，您必須使用前端集區的 IP 位址，或為您的 Front-End server 或 Standard Edition server 進行單一伺服器的準備。 請記住，您的伺服器也可能會在負載平衡器的背後，或使用反向 proxy。 請記下可遵循下列步驟的 IP 位址。

5.  您也需要確認主機 A IPv6) 記錄的 (AAAA 是否存在於您的外部 Web 服務完整功能變數名稱 (FQDN) 如 lyncwebextpool01.contoso.com (，或您的單一伺服器 Lync 安裝的 IP 位址（如果您沒有前端集區）。 如先前的步驟所述，如果您沒有 Director 集區，則需要下列步驟。

6.  現在，在您的外部 DNS 提供者適當的格式中，選擇建立 **新主機 a 或 AAAA** (的選項。這可能是功能表選項或連結，視 DNS 提供者) 的格式而定。

7.  應該有輸入 **名稱**的地方，請輸入 lyncdiscover 做為外部自動探索服務 URL 的主機名稱。

8.  您也應該會有一個 **Ip 位址** 文字方塊，您可以在這裡為 Director 集區 (輸入 ip。例如，lyncwebexdir01.contoso.com) 或可能是集區的負載平衡器 (或反向 proxy ip，會產生相同) ，然後按一下 [確定] 或 [採取外部 DNS 中的任何動作，以接受此專案的建立。 如以上的步驟4所述，如果您沒有 Director 集區，則需要根據需要使用您設定的前端集區 IP 位址或單一伺服器的 IP 位址。

9.  您必須在 Lync 2013 環境所支援的每個 SIP 網域的正向對應區域中，建立新的自動探索 A 或 AAAA 記錄。

</div>

</div>

<span> </span>

</div>

</div>

</div>

