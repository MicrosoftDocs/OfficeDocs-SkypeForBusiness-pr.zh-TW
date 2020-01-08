---
title: Lync Server 2013：受支援的虛擬化技術與已知限制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Supported virtualization technologies and known limitations
ms:assetid: 6d3d749d-e840-4c05-afae-d6e69e7616aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204982(v=OCS.15)
ms:contentKeyID: 48184428
ms.date: 02/07/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1b5c99151be45f70d1d95fa0a89835ebb6f7d352
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977648"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-virtualization-technologies-and-known-limitations-in-lync-server-2013"></a>Lync Server 2013 中受支援的虛擬化技術與已知限制

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2017-02-06_

Lync VDI 外掛程式可支援音訊及視頻通話（支援的虛擬化技術）。 這會在[Microsoft lync 2010 白皮書的用戶端虛擬化](https://go.microsoft.com/fwlink/?linkid=330447)中擴充 Microsoft lync Server 2010 所列的功能。 在遵守標準電話規章的情況下，也包含對 E911 的支援。 下列各節說明 Lync VDI 外掛程式所支援的虛擬化技術和已知的功能限制。

<div>

## <a name="support-for-virtualization-technologies"></a>對虛擬化技術的支援

Lync VDI 外掛程式支援個人虛擬桌面案例中的完整桌面遠端作業，但在遠端桌面會話案例中則不支援。 這些案例的描述如下：

  - **支援：個人化的虛擬桌面或虛擬桌面基礎結構（VDI）。**   在這種情況下，每個使用者都會登入可自訂的虛擬桌面電腦，並能夠在桌上型電腦上儲存跨會話的檔案。 Microsoft 遠端桌面服務、VMware 地平線視圖和 Citrix XenDesktop 是已經過測試，可搭配 Lync 使用的實現。 如需有關已由 Microsoft 測試的供應商專用 VDI 環境及用戶端硬體的相關資訊，請參閱[Microsoft Lync 合格的基礎結構](https://go.microsoft.com/fwlink/?linkid=313435)。

  - **不支援： [遠端桌面會話]。**   在這種情況下，每個使用者都會登入不能自訂的一般虛擬桌面會話。 實作範例包括 Microsoft 遠端桌面工作階段 (RDSH) 和結合 Citrix 接收器的 Citrix XenApp。

Lync VDI 外掛程式不支援其他虛擬化技術（例如應用程式虛擬化），可讓您使用應用程式，而不需要在本機安裝完整的應用程式。 範例實現包括 Citrix XenApp 和 Microsoft Application Virtualization （App-v）。 不支援應用程式流式處理、應用程式遠端處理及混合式虛擬化模式（例如，完整桌面遠端處理中的應用程式遠端處理）。

若要允許擴充性，Lync VDI 外掛程式的設計目的是使用稱為「動態虛擬通道」（DVCs）的平臺無關 Api。 針對 Lync 未明確支援的案例，請參閱來自 VDI 解決方案提供者的支援聲明。

</div>

<div>

## <a name="known-feature-limitations"></a>已知的功能限制

當您在 VDI 環境中使用 Lync 2013 時，以下是已知的限制：

  - 通話委派與回應群組代理匿名功能的支援有限。

  - 不支援以下功能：
    
      - 整合式音訊裝置及視訊裝置調整頁面。
    
      - 多重檢視視訊。
    
      - 錄製交談。
    
      - 遠端桌面服務（RDS）。
    
      - 匿名加入會議（也就是加入不與您的組織聯盟之組織託管的 Lync 會議）。
    
      - 將 Lync VDI 外掛程式與 Lync Phone Edition 裝置搭配使用。
    
      - 在網路中斷連線的情況下延續通話。
    
      - 自訂鈴聲及通話保留音樂功能。

  - 在 Office 365 環境中不支援 Lync VDI 外掛程式。

</div>

</div>

<span> </span>

</div>

</div>

</div>

