---
title: Lync Server 2013：其他伺服器支援和需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Additional server support and requirements
ms:assetid: 7622986b-abd6-4f45-8b5b-d5e2368521e8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398577(v=OCS.15)
ms:contentKeyID: 48184535
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 29f2d1a1b728fcec84f0aed70f00f1143c70c490
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975508"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="additional-server-support-and-requirements-in-lync-server-2013"></a>Lync Server 2013 中的其他伺服器支援和需求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-12-09_

除了本支援檔的其他章節所述的軟體支援之外，Lync Server 2013 還有下列支援限制：

  - Lync Server 2013 支援針對特定伺服器角色的網域名稱系統（DNS）和硬體負載平衡。 它也支援針對轉送伺服器的應用程式負載平衡（在適當的位置）。 如需每個使用時間的詳細資訊，請參閱規劃檔。

  - Lync Server 2013 使用通訊群組清單展開通訊協定（DLX）來展開通訊群組清單。 這個通訊協定也會指定用來取得通訊群組清單成員資格的 web 服務方法。 Microsoft Exchange Server 支援沒有靜態指派成員的動態群組。 相反地，它們會儲存在展開群組時評估的查詢。 DLX 不支援動態通訊群組清單。 此 DLX 限制適用于所有版本的 Lync Server。

  - [啟用使用者] 嚮導不支援將非英文字元自動轉換成與 SIP 相容的 URI，因此您必須手動修改 SIP 位址。

  - 針對執行防毒軟體的伺服器，請參閱[Lync Server 2013 的防病毒掃描排除](lync-server-2013-antivirus-scanning-exclusions.md)程式，以取得建議的病毒排除及其他安全性相關建議。

  - 如果您使用的是 IPsec，我們建議您在用於音訊與視頻流量的埠範圍停用 IPsec。 如需詳細資訊，請參閱規劃檔中的[Lync Server 2013 中的 IPsec 例外](lync-server-2013-ipsec-exceptions.md)狀況。

  - 如果您的組織使用的是服務品質（QoS）基礎結構，媒體子系統就是設計來在這個現有的基礎結構中運作。 如需有關實施 QoS 的詳細資料，請參閱在作業檔中[管理 Lync Server 2013 中的服務品質（QoS）](lync-server-2013-managing-quality-of-service-qos.md) 。

  - 支援使用作業系統防火牆。 Lync Server 2013 可管理作業系統防火牆的防火牆例外狀況（Microsoft SQL Server 資料庫軟體除外）。 如需 SQL Server 防火牆需求的詳細資訊，請參閱 SQL Server 檔。

  - 用來實現外部使用者存取支援的外部介面必須位於個別的子網上，*而不*是與內部介面相同的網路上。

  - Lync Server 2013 的 XMPP 功能是由 Microsoft 針對使用 Google 交談的立即訊息同盟進行測試和支援。 針對任何其他 XMPP 系統，請與協力廠商廠商聯繫，確認他們支援 Lync Server 2013 的同盟，以及任何部署或疑難排解建議。

  - 在發行 Lync Server 2013 累計更新：2013年7月，Lync Server 2013 現在支援雙因素驗證。 如需詳細資訊，請參閱[Lync Server 2013 中的雙因素驗證](lync-server-2013-planning-for-and-deploying-two-factor-authentication.md)。

  - 大多數內部伺服器都需要定義為「**開啟驗證**（OAuth）」的憑證類型。 您必須在 [Lync Server 部署嚮導] 的 [**要求中安裝並指派憑證**] 階段，要求並指派 OAuth 憑證。 OAuth 憑證金鑰的最小大小為1024位。 如果您要求密碼長度少於2048位的憑證，可能會顯示警告。 若要避免在強制執行金鑰長度為2048而不是警告的情況下發生問題，強烈建議您在 OAuth 憑證中，永遠使用金鑰長度2048。

  - Lync Server 2013 和 Microsoft Exchange Server 2010 Service Pack 1 （SP1）的運作支援聯邦資訊處理標準（FIPS）140-2 演算法（如果 Windows Server 2008 R2 作業系統已設定為使用 FIPS 140-2 演算法）系統加密。 若要實現 FIPS 支援，您必須設定執行 Lync Server 2013 的每個伺服器以支援它。 如需與 FIPS 相容的演算法以及如何實現 FIPS 支援的詳細資料，請參閱 Microsoft 知識庫文章811833，「系統加密：使用 FIPS 相容的演算法來加密、雜湊及簽署安全設定（在 Windows XP 中以及更新[http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833)版本的 windows 中）。 如需有關 FIPS 140-2 支援的詳細資訊，以及 Exchange 2010 中的限制，請參閱「Exchange 2010 SP1 和支援[http://go.microsoft.com/fwlink/p/?linkId=205335](http://go.microsoft.com/fwlink/p/?linkid=205335)的 Fips 相容性演算法」。

Lync Server 2013 需要在部署之前或期間，在特定元件上安裝其他軟體。 這包括在安裝 Lync Server 2013 期間自動安裝的作業系統、可下載軟體和軟體所提供的軟體。 以下是可能需要的其他軟體清單：

  - Windows Update

  - Windows 身分識別基礎

  - Microsoft .NET 4.5 Framework

  - Microsoft Visual c + + 2012 可轉散發元件
    
    <div>
    

    > [!NOTE]  
    > 安裝 Lync Server 2013 時，系統會自動安裝 Microsoft Visual c + + 2012 可再發行的功能。 您不應該安裝並使用任何其他版本。

    
    </div>

  - URL 重新寫入模組版本2.0 可再發行

  - Windows Media 格式執行時間

  - Windows PowerShell 版本3。0

  - Microsoft Silverlight 4 瀏覽器外掛程式（Silverlight 4.0.50524.0 或 Lync Server [控制台] 的最新版本）

  - Active Directory 網域服務工具

某些軟體需求只適用于特定伺服器角色或元件。 如需這些軟體需求的詳細資訊，請參閱規劃檔中[Lync Server 2013 的其他軟體需求](lync-server-2013-additional-software-requirements.md)。

</div>

<span> </span>

</div>

</div>

</div>

