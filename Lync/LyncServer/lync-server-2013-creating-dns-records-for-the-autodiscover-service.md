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
ms.openlocfilehash: d91c67620a87fdd91a1755592175e8cf2964d259
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741143"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-dns-records-for-the-autodiscover-service-in-lync-server-2013"></a>在 Lync Server 2013 中建立自動探索服務的 DNS 記錄

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-06-20_

您的 Lync 行動使用者將需要您啟用自動探索，以及這部分涉及建立一些網域名稱系統（DNS）記錄。 視您的需求而定，您需要下列各項：

  - 內部 DNS 記錄可支援從貴組織的網路內部連線的行動使用者。

  - 外部或公用的 DNS 記錄，可支援從網際網路連線的行動使用者

為什麼要這麼做？ 您必須為每個 SIP 網域建立內部 DNS 記錄和外部 DNS 記錄。

您建立的 DNS 記錄可以是（主機）記錄或 CNAME 記錄。 為了協助您完成，我們將逐步說明如何在下方建立這些內部和外部 DNS 記錄。 如果您需要進一步瞭解行動使用者的 DNS 需求，您可以查看[Lync Server 2013 中行動裝置的技術需求](lync-server-2013-technical-requirements-for-mobility.md)。

<div>

## <a name="creating-an-internal-dns-cname-record"></a>建立內部 DNS CNAME 記錄

1.  若要建立內部 DNS 記錄，您必須使用網域系統管理員群組成員或 DnsAdmins 群組成員的網域帳戶登入您網路中的 DNS 伺服器。

2.  開啟 [DNS 管理] 管理單元：按一下 [**開始**]，按一下 [**管理工具**]，然後按一下 [ **dns**]。

3.  在 DNS 伺服器的 [主控台樹] 中，展開您的 Lync Server 2013 控制器池與頂層端池安裝所在 Active Directory 網域的 [**正向查閱區域**]。 （例如 contoso. local）。

4.  檢查並查看您的主機 A （IPv6）記錄是否存在於內部 DNS 記錄的主管池，主機 A 記錄應該存在於內部 Web 服務的主管池（例如，lyncwebdir01）內的完整功能變數名稱（FQDN）。 如果您不在這裡，您可能不是使用控制器池，而且您必須使用前端池的 FQDN，或甚至是單一伺服器 FQDN （如果您是設定的話）。

5.  請記住，請檢查並查看內部 DNS 記錄的主機 A （IPv6）記錄是否存在，對於內部 DNS 記錄，必須有主機 A （或 AAAA）記錄，才能供您的前端伺服器的內部 Web 服務 FQDN 使用（例如、lyncwebpool01）。 如果不是，您必須記下前端伺服器或標準版 server 的 FQDN。

6.  知道存在哪個主機 A （或 AAAA）記錄之後，請在您的 DNS 伺服器的主控台樹中，展開您 SIP 網域的**轉寄查閱區域**（例如，contoso.com）。

7.  以滑鼠右鍵按一下 SIP 網功能變數名稱稱，然後按一下 **[新增別名（CNAME）**]。

8.  在 [**別名名稱**] 中，輸入 lyncdiscoverinternal 做為內部自動探索服務 URL 的主機名稱。

9.  在**目標主機的完整功能變數名稱（FQDN）** 中，輸入或流覽至您主管池的內部 WEB 服務 FQDN （例如，lyncwebdir01），然後按一下 **[確定]**。

10. 您必須在 Lync Server 2013 環境支援的每個 SIP 網域的轉寄查閱區域中建立新的自動探索 CNAME 記錄。

</div>

<div>

## <a name="creating-an-external-dns-cname-record"></a>建立外部 DNS CNAME 記錄

1.  若要建立外部 DNS CNAME 記錄，您需要連線到您的公用 DNS 提供者，然後依照我們的步驟進行。 我們無法確切描述您在 DNS 提供者環境中所處的位置，因為可能會有不同的方式管理您的外部 DNS，但我們希望這些步驟有所説明。

2.  使用可在該環境中建立 DNS 記錄的帳戶登入您的外部 DNS 提供者。

3.  您應該已為此環境建立 SIP 網域。 展開此 SIP 網域的**正向查閱區域**，或者根據所使用的外部 DNS 介面來選取它。

4.  您應該已看到主管池（例如 lyncwebexdir01.contoso.com）的主機 A （IPv6）記錄，所以請確認它在那裡。 如果不是，則您可能不是使用控制器池。 如果是這種情況，您必須使用前端池的 FQDN，或者，如果您要針對前端伺服器或標準版伺服器執行這項伺服器的操作。

5.  您也必須確認對於您的外部 Web 服務（例如 lyncwebextpool01.contoso.com），或您的單一伺服器 FQDN （如果您沒有前端池），才會有主機 A （適用于 IPv6 的 AAAA）記錄。 如前一個步驟所述，如果您沒有主管池，您將需要下列其中一項。

6.  現在，在您的外部 DNS 提供者適當的格式中，選擇建立**新別名（CNAME）** 的選項（這可能是功能表選項或連結，視 DNS 提供者的格式而定）。

7.  您應該將 [**別名名稱**] 文字方塊與內部 DNS 一樣，您應該輸入 lyncdiscover 做為外部自動探索服務 URL 的主機名稱。

8.  [目標主機] 文字方塊的**完整功能變數名稱（FQDN）** ，以下是您要在其中輸入主管池的外部 WEB 服務 FQDN （例如，lyncwebexdir01.contoso.com），然後按一下 [確定] 或在外部 DNS 中採取任何動作，即可接受此專案的建立。 如上述步驟4所述，如果您沒有主管池，就必須使用 [前端] 池 FQDN 或您設定的單一伺服器 FQDN （視情況而定）。

9.  您必須在 Lync 2013 環境支援的每個 SIP 網域的轉寄查閱區域中，建立新的自動探索 CNAME 記錄。

</div>

<div>

## <a name="creating-an-internal-dns-a-record"></a>建立內部 DNS A 記錄

1.  若要建立內部 DNS 記錄，請使用網域系統管理員群組成員或 DnsAdmins 群組成員的網域帳戶登入您網路中的 DNS 伺服器。

2.  開啟 [DNS 管理] 管理單元：按一下 [**開始**]，按一下 [**管理工具**]，然後按一下 [ **dns**]。

3.  如果是內部 DNS 記錄，請在 DNS 伺服器的主控台樹中，展開您的 Active Directory 網域（例如 contoso）的**正向查閱區域**，您的 Lync Server 2013 控制器池與頂層端池的安裝位置。

4.  檢查並查看您的主機 A （IPv6）記錄是否存在於內部 DNS 記錄的主管池，主機 A 記錄應該存在於內部 Web 服務的主管池（例如，lyncwebdir01）內的完整功能變數名稱（FQDN）。 如果不在這裡，您可能不是使用主管池，而且您必須使用您的前端池的 IP 位址，或是甚至是單一伺服器 IP 位址（如果您是設定的話）。

5.  請記住，請檢查並查看內部 DNS 記錄的主機 A （IPv6）記錄是否存在，對於內部 DNS 記錄，必須有主機 A （或 AAAA）記錄，才能供您的前端伺服器的內部 Web 服務 FQDN 使用（例如、lyncwebpool01）。 如果不是，您必須記下前端伺服器或標準版伺服器的 IP 位址。

6.  知道存在哪個主機 A （或 AAAA）記錄之後，請在您的 DNS 伺服器的主控台樹中，展開您 SIP 網域的**轉寄查閱區域**（例如，contoso.com）。

7.  以滑鼠右鍵按一下 SIP 網功能變數名稱稱，然後按一下 **[新增主機（A 或 AAAA）**]。

8.  在 [**名稱**] 中，輸入 lyncdiscoverinternal 做為內部自動探索服務 URL 的主機名稱。

9.  在 [ **IP 位址**] 中，輸入主管的內部 WEB 服務 IP 位址（或者，如果您使用負載平衡器，請輸入控制器負載平衡器的虛擬 IP （VIP））。 如上述步驟4所述，如果您不是使用主管，您可能需要輸入前端伺服器或標準版伺服器的 IP 位址，或者，如果您使用負載平衡器，請輸入前端池負載平衡器的 VIP。

10. 按一下 [**新增主機**]，然後按一下 **[確定]**。

11. 若要建立額外的 A 或 AAAA 記錄，請重複步驟8到10，請記住，您必須在 Lync Server 2013 環境支援的每個 SIP 網域的轉寄查閱區域中，建立新的自動探索 A 或 AAAA 記錄。

12. 完成建立（適用于 IPv6、AAAA）記錄之後，按一下 [**完成**]。

</div>

<div>

## <a name="creating-an-external-dns-a-record"></a>建立外部 DNS A 記錄

1.  若要建立外部 DNS 記錄，請連接到您的公用 DNS 提供者，然後依照我們的步驟進行。 我們無法確切描述您在 DNS 提供者環境中所處的位置，因為可能會有不同的方式管理您的外部 DNS，但我們希望這些步驟有所説明。

2.  您必須以帳戶的身分登入，才能在該環境中建立 DNS 記錄。

3.  針對外部 DNS 記錄，請在 DNS 伺服器的主控台樹中，展開您 SIP 網域的**正向查閱區域**（例如，contoso.com）。 針對外部 DNS 記錄，請在 DNS 伺服器的主控台樹中，展開您 SIP 網域的**正向查閱區域**（例如，contoso.com）。

4.  您應該已看到主管池（例如 lyncwebexdir01.contoso.com）的主機 A （IPv6）記錄，然後確認它在那裡，以及 IP 位址是什麼。 如果不是，則您可能不是使用控制器池。 如果是這種情況，您必須使用前端池的 IP 位址，或者，如果您要針對前端伺服器或標準版伺服器執行這項單一伺服器的作業，就必須使用它。 請記住，您的伺服器也可能位於負載平衡器，或使用反向 proxy。 請記下 IP 位址，並依照下列步驟進行。

5.  您也必須確認主機 A （IPv6）記錄存在於您的外部 Web 服務（例如 lyncwebextpool01.contoso.com）中，或您的單一伺服器 Lync 安裝的 IP 位址（如果您使用的是您）。沒有 [前端] 池。 如前一個步驟所述，如果您沒有主管池，您將需要下列其中一項。

6.  現在，在您的外部 DNS 提供者適當的格式中，選擇建立**新主機 a 或 AAAA**的選項（這可能是功能表選項或連結，視 DNS 提供者的格式而定）。

7.  應該有一個輸入**名稱**的位置，輸入 lyncdiscover 做為外部自動探索服務 URL 的主機名稱。

8.  您也應該有一個**Ip 位址**文字方塊，您可以在這裡輸入您的主管池（例如，lyncwebexdir01.contoso.com）的 ip，或者可能是您的池負載平衡器（或產生相同的反向 proxy ip），然後按一下 [確定] 或在外部 DNS 中採取任何動作來接受此專案的建立。 如上述步驟4所述，如果您沒有主管池，您必須使用 [前端] 池 IP 位址或您已設定的單伺服器 IP 位址（視情況而定）。

9.  您必須在 Lync 2013 環境支援的每個 SIP 網域的轉寄查閱區域中，建立新的自動探索 A 或 AAAA 記錄。

</div>

</div>

<span> </span>

</div>

</div>

</div>

