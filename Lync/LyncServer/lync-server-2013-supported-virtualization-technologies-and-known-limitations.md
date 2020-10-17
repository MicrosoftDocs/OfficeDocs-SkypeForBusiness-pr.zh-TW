---
title: Lync Server 2013：支援的虛擬化技術與已知限制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported virtualization technologies and known limitations
ms:assetid: 6d3d749d-e840-4c05-afae-d6e69e7616aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204982(v=OCS.15)
ms:contentKeyID: 48184428
ms.date: 02/07/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 61d2d884566c21933e00dd3897f5fe394b4a2624
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523930"
---
# <a name="supported-virtualization-technologies-and-known-limitations-in-lync-server-2013"></a>Lync Server 2013 中支援的虛擬化技術與已知限制

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2017-02-06_

Lync VDI 外掛程式允許音訊和視頻通話支援的虛擬化技術。 這會在 [Microsoft lync 2010 白皮書的用戶端虛擬化](https://go.microsoft.com/fwlink/?linkid=330447) 中，擴充 Microsoft lync Server 2010 所列的功能。 在遵守標準電話規定時，也會包含對 E911 的支援。 下列各節說明 Lync VDI 外掛程式支援的虛擬化技術與已知的功能限制。

<div>

## <a name="support-for-virtualization-technologies"></a>虛擬化技術的支援

Lync VDI 外掛程式支援個人虛擬桌面案例中的完整桌面遠端處理，但不支援在遠端桌面會話案例中。 您可以將這些案例描述如下：

  - **支援：個人化虛擬桌面或虛擬桌面基礎結構 (VDI) 。**    在此案例中，每一位使用者都登入至可自訂的虛擬桌面機，而且能夠將保留在會話中的檔案儲存在桌面機上。 Microsoft 遠端桌面服務、VMware 地平線模式，以及 Citrix XenDesktop 是已測試為搭配 Lync 使用的實施方案。 如需廠商特有的 VDI 環境及已由 Microsoft 測試的用戶端硬體資訊，請參閱 [Microsoft Lync 的基礎結構限定](https://go.microsoft.com/fwlink/?linkid=313435)。

  - **不支援：遠端桌面會話。**    在此案例中，每一位使用者都登入無法自訂的一般虛擬桌面會話。 範例實施包括 Microsoft 遠端桌面會話 (RDSH) 和 Citrix XenApp 與 Citrix 接收器結合使用。

Lync VDI 外掛程式不支援其他虛擬化技術（例如 application virtualization），允許使用應用程式，而不需要在本機安裝完整的應用程式。 範例實現包括 Citrix XenApp 和 Microsoft Application Virtualization (App-V) 。 應用程式流式處理、應用程式遠端處理和混合虛擬化模式 (例如，不支援完整桌面遠端) 中的應用程式遠端處理。

為了允許擴充，Lync VDI 外掛程式設計為使用獨立于平臺的 APIs，稱為動態虛擬通道 (Dvc) 。 如果是 Lync 未明確支援的案例，請參閱 VDI 解決方案提供者的支援聲明。

</div>

<div>

## <a name="known-feature-limitations"></a>已知的功能限制

當您在 VDI 環境中使用 Lync 2013 時，已知的限制如下：

  - 「呼叫委派」和「回應群組代理程式」匿名功能的支援有限。

  - 不支援以下功能：
    
      - 整合式音訊裝置及視訊裝置調整頁面。
    
      - 多 view 影片。
    
      - 錄製交談。
    
      - 遠端桌面服務 (RDS) 。
    
      - 以匿名方式加入會議 (也就是說，加入由未與您) 組織建立同盟之組織所主控的 Lync 會議。
    
      - 使用 Lync VDI 外掛程式和 Lync Phone Edition 裝置。
    
      - 在網路中斷連線的情況下延續通話。
    
      - 自訂鈴聲和暫止的音樂功能。

  - 在 Microsoft 365 或 Office 365 環境中不支援 Lync VDI 外掛程式。

</div>

</div>

<span> </span>

</div>

</div>

</div>

