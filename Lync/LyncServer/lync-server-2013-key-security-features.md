---
title: Lync Server 2013：主要安全性功能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Key security features in Lync Server 2013
ms:assetid: bf2a3b8f-73c6-47e1-8c9e-ca1dc1a502bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn342829(v=OCS.15)
ms:contentKeyID: 56107266
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 53a6d9e23442cb127f0f08849e18f1d63bae76d6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974060"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="key-security-features-in-lync-server-2013"></a>Lync Server 2013 的主要安全性功能

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-07-18_

Lync Server 2013 包含數種安全性功能，包括伺服器到伺服器驗證、以角色為基礎的存取控制，以及集中式儲存配置資料。

這篇文章提供 Lync Server 2013 安全性的高層次概覽。

<div>

## <a name="key-security-features-in-lync-server-2013"></a>Lync Server 2013 的主要安全性功能

安全性是一個非常廣泛的主題。 每個 Lync Server 2013 的功能，以及組成 Lync 生態系統的資料庫、服務和硬體，都能達到安全性。 本文概述 Lync Server 2013 中的部分功能，特別是針對安全性設計的。

<div>

## <a name="planning-and-design-tools"></a>規劃和設計工具

Lync Server 2013 提供兩種工具，可協助規劃及設計並減少 misconfiguring Lync Server 元件的機率。

  - **拓撲規劃工具**自動化了許多拓撲設計程式。 您可以將規劃工具的結果匯出至 [拓撲建立器]，這是安裝每個執行 Lync Server 2013 的伺服器所需的工具。

  - **拓撲**建立器會將所有配置資訊儲存在中央管理儲存區中。

如需這些工具的詳細資訊，請參閱[規劃 Lync Server 2013](lync-server-2013-planning.md)。

</div>

<div>

## <a name="central-management-store"></a>中央管理存放區

在 Lync Server 2013 中，伺服器與服務的設定資料是集中式管理儲存體的一部分。 [中央管理] 商店提供資料的強健、schematized 儲存，以定義、設定、維護、管理、描述及操作 Lync Server 部署。 它也會驗證資料，以確保配置一致性。 此設定資料的所有變更都會出現在中央管理商店，消除「不同步」問題。

唯讀複本會將資料複製到拓撲中的所有伺服器，包括 Edge 伺服器和 Survivable 分支裝置。 複製是由預設會在網路服務內容下執行的服務所管理，可減少電腦上簡單使用者的權利和許可權。

</div>

<div>

## <a name="server-to-server-authentication"></a>伺服器對伺服器驗證

在 Lync Server 2013 中，您可以使用開啟授權（OAuth）通訊協定，在伺服器之間設定驗證。 例如，您可以設定 Lync Server 2013，以使用執行 Exchange Server 2013 的伺服器進行驗證。 使用 OAuth 通訊協定，Lync server 和 Exchange 伺服器可以相互信任。 這能讓您以流暢的方式整合產品。 如需詳細資訊，請參閱[在 Lync server 2013 中管理伺服器間驗證（OAuth）與合作夥伴應用程式](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)

</div>

<div>

## <a name="windows-powershell-based-management-and-web-based-management-interface"></a>Windows PowerShell 式管理和網路式管理介面

Lync Server 2013 提供功能強大的管理介面（在 Windows PowerShell 命令列介面上建立）。 它包含管理安全性的 Cmdlet，而且預設會啟用 Windows PowerShell 安全性功能，讓使用者不會輕易或無意中執行腳本。 這表示軟體預設值會設定為自動協助最大化安全性並減少攻擊途徑。 如需 Lync Server 2013 中的 Windows PowerShell 管理支援的詳細資訊，請參閱[Lync server 2013 管理命令](lync-server-2013-lync-server-management-shell.md)介面。

</div>

<div>

## <a name="role-based-access-control-rbac"></a>以角色為基礎的存取控制（RBAC）

Microsoft Lync Server 2013 提供以角色為基礎的存取控制（RBAC），可讓您委派管理工作，同時維持高安全性的標準。 您可以使用 RBAC 遵循「最低許可權」的原則，在此原則中，使用者只會得到他們工作所需的管理許可權。 Lync Server 2013 引入了建立新角色的功能，也是修改現有角色的功能。 如需詳細資訊，請參閱[在 Lync Server 2013 中規劃以角色為基礎的存取控制](lync-server-2013-planning-for-role-based-access-control.md)。

</div>

</div>

<div>

## <a name="network-address-translation-nat"></a>網路位址轉譯（NAT）

Lync Server 2013 不支援在 Edge 伺服器的內部介面使用網路位址轉譯（NAT），但它支援將存取邊緣服務、Web 會議邊緣服務的外部介面與路由器或防火牆後面的 A/V 邊緣服務搭配執行，可針對單一和縮放的合併邊緣伺服器拓撲進行網路位址轉譯（NAT）。 在硬體負載平衡器後的多個邊緣伺服器無法使用 NAT。 如果有多個邊緣伺服器在其外部介面上使用 NAT，則需要網功能變數名稱稱系統（DNS）負載平衡。 接著，您可以使用 DNS 負載平衡，在 Edge 伺服器池中減少每個邊緣伺服器的公用 IP 位址數目。 如需詳細資訊，請參閱[在 Lync Server 2013 中規劃外部使用者存取](lync-server-2013-planning-for-external-user-access.md)。

<div>


> [!NOTE]  
> 如果您是與已安裝 Microsoft Office 通訊伺服器2007部署的企業聯盟，而且您需要在企業與同盟企業之間使用音訊/視頻，則埠需求就會是部署的較舊版本的邊緣伺服器的需求。 例如，必須針對兩個企業開啟這些較舊版本所需的埠範圍，直到聯盟合作夥伴將其 Edge 伺服器升級到 Lync Server 2013 為止。 此時，您可以根據新設定來審查並減少埠需求。



</div>

</div>

<div>

## <a name="simplified-certificates-for-edge-servers"></a>簡化的邊緣伺服器憑證

[部署嚮導] 可自動填入消費者名稱（SNs）和消費者備用名稱（San），減少包括不必要和可能不安全的專案的可能性。

</div>

<div>

## <a name="trustworthy-computing-security-development-lifecycle-sdl"></a>可信計算安全性開發週期（SDL）

Lync Server 2013 的設計與開發符合 Microsoft 高可信計算安全性開發週期（SDL），其說明如下<http://go.microsoft.com/fwlink/?linkid=68761>。

  - **根據設計**   ，建立更安全的整合通訊系統中的第一個步驟，就是設計威脅模型並測試每個功能的設計。 此外，Microsoft 還會在設計的行為以外執行測試，以找出意外產品行為所產生的安全性漏洞。 編碼程式與做法內建了多個安全性相關的改良功能。 在將程式碼簽入最終產品之前，組建時間工具會偵測緩衝區溢位及其他潛在安全性威脅。 當然，可能無法針對所有未知的安全性威脅進行設計。 任何系統都不能保證完整的安全性。 不過，由於產品開發採用來自開始的安全設計原則，因此 Lync Server 2013 將業界標準安全技術納入其架構的基本部分。

  - **預設為可信**   ： Lync Server 2013 的網路通訊是經過加密的。 由於所有伺服器都使用憑證和 Kerberos 驗證、TLS、安全的即時傳輸通訊協定（SRTP），以及其他業界標準的加密技術，包括128位進階加密標準（AES）加密，幾乎都是所有 Lync網路上的伺服器資料受到保護。 此外，角色式存取控制能讓您部署執行 Lync Server 2013 的伺服器，讓每個伺服器角色只執行服務，而且只有與這些服務相關聯的許可權，這些都適用于伺服器角色。

  - **受部署**   信任：所有 Lync Server 2013 檔都包含最佳做法與建議，以協助您決定並設定您的部署的最佳安全等級，並評估啟用非預設選項的安全性風險。

</div>

</div>

<span> </span>

</div>

</div>

</div>

