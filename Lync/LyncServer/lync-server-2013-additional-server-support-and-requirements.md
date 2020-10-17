---
title: Lync Server 2013：其他伺服器支援和需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Additional server support and requirements
ms:assetid: 7622986b-abd6-4f45-8b5b-d5e2368521e8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398577(v=OCS.15)
ms:contentKeyID: 48184535
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cd3dad53b954fed8e1513ff9704b35c3c4831ffd
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521250"
---
# <a name="additional-server-support-and-requirements-in-lync-server-2013"></a>Lync Server 2013 中的其他伺服器支援和需求

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-12-09_

除了此支援檔的其他章節所述的軟體支援之外，Lync Server 2013 還提供下列支援限制：

  - Lync Server 2013 支援網域名稱系統 (DNS) 和特定伺服器角色的硬體負載平衡。 也支援對中繼伺服器使用應用程式負載平衡 (若情況允許)。 如需各項目使用時機的詳細資訊，請參閱＜規劃＞文件。

  - Lync Server 2013 使用通訊群組清單擴充通訊協定 (DLX) 來展開通訊群組清單。 此通訊協定也會指定為了取得通訊群組清單的成員資格而使用的 Web 服務方法。 Microsoft Exchange Server 支援未以靜態方式指派成員的動態群組。 這些群組中儲存在展開群組時才會評估的查詢。 DLX 不支援動態通訊群組清單。 此 DLX 限制適用于所有的 Lync Server 版本。

  - [啟用使用者精靈] 不支援自動將非英文字元轉換成符合 SIP 標準的 URI，因此您必須手動修改 SIP 位址。

  - 針對執行防毒軟體的伺服器，請參閱 [Lync Server 2013 的防病毒掃描排除](lync-server-2013-antivirus-scanning-exclusions.md) ，以取得建議的病毒排除和其他安全性相關建議。

  - 如果您有使用 IPsec，我們建議您針對音訊與視訊流量所使用的連接埠範圍停用 IPsec。 如需詳細資訊，請參閱規劃檔中的 [IPsec 的 Lync Server 2013](lync-server-2013-ipsec-exceptions.md) 中的例外狀況。

  - 如果您的組織使用的是服務品質 (QoS) 基礎結構，則媒體子系統將會設計成配合此現有基礎結構運作。 如需有關執行 QoS 的詳細資訊，請參閱 Operations 檔中的 [管理 Lync Server 2013 中的服務品質 (QoS) ](lync-server-2013-managing-quality-of-service-qos.md) 。

  - 支援使用作業系統防火牆。 Lync Server 2013 管理作業系統防火牆的防火牆例外狀況，但 Microsoft SQL Server 資料庫軟體除外。 如需 SQL Server 防火牆需求的詳細資訊，請參閱 SQL Server 文件。

  - 用來實作外部使用者存取支援的外部介面必須位於個別子網路，而非** 與內部介面位於相同網路。

  - Lync Server 2013 的 XMPP 功能會經過測試，並受 Microsoft 支援，以進行與 Google 交談的立即訊息同盟。 對於任何其他 XMPP 系統，請聯繫協力廠商廠商，以確認其支援與 Lync Server 2013 的同盟，以及任何部署或疑難排解建議。

  - 使用 Lync Server 2013 累計更新的發行：7月2013，Lync Server 2013 現在支援雙因素驗證。 如需詳細資訊，請參閱 [Lync Server 2013 中的兩要素驗證](lync-server-2013-planning-for-and-deploying-two-factor-authentication.md)。

  - 大多數內部伺服器都需要以「 **開啟驗證** (」 OAuth) 定義的憑證類型。 在 [Lync Server 部署嚮導] 的 [ **要求、安裝與指派憑證** ] 階段中，需要要求並指派 OAuth 憑證。 OAuth 憑證金鑰的大小下限為1024位。 如果您要求密碼長度小於2048位的憑證，則會顯示警告。 為了避免發生潛在問題（而不是警告的金鑰長度為2048），強烈建議您在 OAuth 憑證中，永遠使用金鑰長度2048。

  - Lync Server 2013 和 Microsoft Exchange Server 2010 Service Pack 1 (SP1) 運作支援聯邦資訊處理標準 (FIPS) 140-2 演算法（如果 Windows Server 2008 R2 作業系統設定為使用 FIPS 140-2 演算法進行系統加密）。 若要實施 FIPS 支援，您必須設定每台執行 Lync Server 2013 的伺服器以支援它。 如需 FIPS 相容的演算法及如何實施 FIPS 支援的詳細資訊，請參閱 Microsoft 知識庫文章811833：在 Windows XP 和更新版本的 Windows 中，使用 FIPS 相容演算法進行加密、雜湊和簽署安全性設定 [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833) 。 如需 Exchange 2010 中的 FIPS 140-2 支援和限制的詳細資訊，請參閱《 Exchange 2010 SP1 及支援 FIPS 相容的演算法》 [https://go.microsoft.com/fwlink/p/?linkId=205335](https://go.microsoft.com/fwlink/p/?linkid=205335) 。

Lync Server 2013 需要在部署之前或之後，在特定元件上安裝其他軟體。 這包括在安裝 Lync Server 2013 期間自動安裝的作業系統、可下載軟體和軟體中所提供的軟體。 以下列出其他可能需要的軟體：

  - Windows Update

  - Windows Identity Foundation

  - Microsoft .NET 4.5 Framework

  - Microsoft Visual c + + 2012 可轉散發元件
    
    <div>
    

    > [!NOTE]  
    > 當您安裝 Lync Server 2013 時，會自動安裝 Microsoft Visual c + + 2012 可轉散發元件。 您不應該安裝和使用任何其他版本。

    
    </div>

  - URL Rewrite Module Version 2.0 可轉散發套件

  - Windows Media Format Runtime

  - Windows PowerShell 版本3。0

  - Microsoft Silverlight 4 瀏覽器外掛程式 (Lync Server 控制台需要 Silverlight 4.0.50524.0 或最新的版本)

  - Active Directory 網域服務工具

其中有些軟體需求僅適用於特定伺服器角色或元件。 如需這些軟體需求的詳細資訊，請參閱規劃檔中的 [Lync Server 2013 其他軟體需求](lync-server-2013-additional-software-requirements.md) 。

</div>

<span> </span>

</div>

</div>

</div>

