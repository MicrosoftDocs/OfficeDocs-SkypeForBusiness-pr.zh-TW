---
title: Lync Server 2013：重要安全性功能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Key security features in Lync Server 2013
ms:assetid: bf2a3b8f-73c6-47e1-8c9e-ca1dc1a502bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn342829(v=OCS.15)
ms:contentKeyID: 56107266
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20205bb401132143b0bcda28343e4ae3bcfd93b2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186776"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="key-security-features-in-lync-server-2013"></a>Lync Server 2013 中的重要安全性功能

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-07-18_

Lync Server 2013 包含數個安全性功能，包括伺服器對伺服器驗證、角色型存取控制，以及設定資料的集中式儲存區。

本文提供 Lync Server 2013 安全性的高層次概述。

<div>

## <a name="key-security-features-in-lync-server-2013"></a>Lync Server 2013 中的重要安全性功能

安全性是非常廣泛的主題。 每個 Lync Server 2013 功能的安全性，以及構成 Lync 生態系統之資料庫、服務和硬體的安全性。 本文概述 Lync Server 2013 中的部分功能，尤其是針對安全性設計。

<div>

## <a name="planning-and-design-tools"></a>規劃及設計工具

Lync Server 2013 提供兩個工具，可協助規劃及設計，並減少 kerberos Lync Server 元件的機率。

  - **拓撲規劃工具**會使大部分的拓撲設計程式自動化。 您可以將規劃工具的結果匯出至拓撲產生器，這是安裝每一部執行 Lync Server 2013 的伺服器所需的工具。

  - **拓撲**產生器會將所有設定資訊儲存在中央管理存放區中。

如需這些工具的詳細資訊，請參閱[規劃 Lync Server 2013](lync-server-2013-planning.md)。

</div>

<div>

## <a name="central-management-store"></a>Central Management Store

在 Lync Server 2013 中，有關伺服器和服務的設定資料是中央管理存放區的一部分。 中央管理存放區為定義、設定、維護、管理、描述及操作 Lync Server 部署所需的資料提供了可靠的 schematized 儲存。 它也驗證資料，以確保設定一致性。 對此設定資料所做的所有變更都會發生在中央管理存放區，消除「不同步」的問題。

資料的唯讀複本會複製到拓撲中的所有伺服器，包括 Edge Server。 複寫是由預設會在網路服務內容下執行的服務所管理，可減少電腦上的簡易使用者的權利和許可權。

</div>

<div>

## <a name="server-to-server-authentication"></a>Server-to-Server 驗證

在 Lync Server 2013 中，您可以使用「開啟授權 (OAuth) 通訊協定，在伺服器之間設定驗證。 例如，您可以設定 Lync Server 2013，以與執行 Exchange Server 2013 的伺服器進行驗證。 Lync server 與 Exchange server 可以相互信任，使用 OAuth 通訊協定。 這讓您能夠以無縫的方式整合產品。 如需詳細資訊，請參閱[管理伺服器對伺服器驗證 (OAuth) 和夥伴應用程式的 Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)

</div>

<div>

## <a name="windows-powershell-based-management-and-web-based-management-interface"></a>Windows PowerShell 型管理和以網路為基礎的管理介面

Lync Server 2013 提供強大的管理介面，以 Windows PowerShell 命令列介面為基礎。 它包含管理安全性的 Cmdlet，預設會啟用 Windows PowerShell 安全性功能，讓使用者無法輕易或無意中執行腳本。 這表示軟體預設值設為自動協助最大化安全性，並減少攻擊途徑。 如需 Lync Server 2013 中 Windows PowerShell 管理支援的詳細資訊，請參閱[Lync server 2013 管理命令](lync-server-2013-lync-server-management-shell.md)介面。

</div>

<div>

## <a name="role-based-access-control-rbac"></a>角色型存取控制 (RBAC)

Microsoft Lync Server 2013 提供以角色為基礎的存取控制 (RBAC) ，可讓您委派管理工作，同時維持高安全性標準。 您可以使用 RBAC 遵循「最低許可權」的原則，讓使用者只會獲得其工作所需的系統管理許可權。 Lync Server 2013 引進的功能，可建立新的角色，也可修改現有角色的功能。 如需詳細資訊，請參閱[在 Lync Server 2013 中規劃以角色為基礎的存取控制](lync-server-2013-planning-for-role-based-access-control.md)。

</div>

</div>

<div>

## <a name="network-address-translation-nat"></a>網路位址轉譯 (NAT) 

Lync Server 2013 不支援在 Edge Server 的內部介面上使用網路位址轉譯 (NAT) ，但它不支援將 Access Edge service、Web 會議 Edge service 和 A/V Edge service 的外部介面放在路由器或防火牆後面，可對單一及調整式合併 Edge Server 拓撲執行網路位址轉譯 (NAT) 。 硬體負載平衡器背後的多部 Edge Server 無法使用 NAT。 如果有多部 Edge Server 在其外部介面上使用 NAT，則需要網域名稱系統 (DNS) 負載平衡。 反過來，使用 DNS 負載平衡可讓您減少 Edge Server 集區中每一 Edge Server 的公用 IP 位址數目。 如需詳細資訊，請參閱[在 Lync Server 2013 中規劃外部使用者存取](lync-server-2013-planning-for-external-user-access.md)。

<div>


> [!NOTE]  
> 如果您與具有 Microsoft Office 通訊伺服器2007部署的企業同盟，且您需要在您的企業和同盟企業之間使用音訊/視頻，則埠需求將會是部署的舊版 Edge Server 的需求。 例如，必須針對這兩種企業開啟這些舊版本所需的埠範圍，直到同盟合作夥伴將其 Edge Server 升級至 Lync Server 2013 為止。 在這個階段，您可以根據新設定來檢查和縮短埠需求。



</div>

</div>

<div>

## <a name="simplified-certificates-for-edge-servers"></a>簡化 Edge Server 的憑證

部署嚮導可自動將主體名稱填入 (SNs) 和主體替代名稱 (SANs) ，以減少包含不必要的可能不安全專案的可能性。

</div>

<div>

## <a name="trustworthy-computing-security-development-lifecycle-sdl"></a>可信賴的計算安全性開發生命週期 (SDL) 

Lync Server 2013 的設計和開發符合 Microsoft 可信賴的計算安全性開發生命週期 (SDL) ，如所述 <https://go.microsoft.com/fwlink/?linkid=68761> 。

  - **以設計**     為可信建立更安全的整合通訊系統的第一步是設計威脅模型，並在設計時測試每項功能。 此外，Microsoft 會在設計行為以外執行測試，以找出意外產品行為所產生的安全性弱點。 編碼程式和作法內建了多種安全性相關的增強功能。 組建時間工具會在將程式碼存回最終產品之前，偵測緩衝區溢位及其他潛在安全性威脅。 當然，不可能針對所有未知的安全性威脅進行設計。 任何系統都不能保證完整的安全性。 不過，由於產品開發採用來自「開始」的安全性設計原則，所以 Lync Server 2013 採用業界標準安全性技術作為其架構的基礎部分。

  - **預設**     為可信依預設，Lync Server 2013 中的網路通訊都會加密。 由於所有伺服器都使用憑證和 Kerberos 驗證、TLS、安全即時傳輸通訊協定 (SRTP) ，以及其他業界標準的加密技術（包括128位的進階加密標準 (AES) 加密），實際上所有的 Lync Server 資料都會在網路上受到保護。 此外，以角色為基礎的存取控制可讓您部署執行 Lync Server 2013 的伺服器，如此一來，每個伺服器角色都只執行服務，而且只會有與這些服務相關的許可權，這些都適用于伺服器角色。

  - **信任的部署**    所有的 Lync Server 2013 檔都包含最佳作法和建議，可協助您決定及設定部署的最佳安全性層級，並評估啟用非預設選項的安全性風險。

</div>

</div>

<span> </span>

</div>

</div>

</div>

