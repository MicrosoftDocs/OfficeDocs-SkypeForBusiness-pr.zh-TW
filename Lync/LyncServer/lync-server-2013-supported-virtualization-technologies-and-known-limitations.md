---
title: Lync Server 2013： 支援虛擬化技術和已知的限制
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
ms.openlocfilehash: eea1c79ae4d614e78af92cba9cf25a30a370d5a9
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142329"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="supported-virtualization-technologies-and-known-limitations-in-lync-server-2013"></a>支援的虛擬化技術和 Lync Server 2013 中的已知的限制

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2017年-02-06_

Lync VDI 外掛程式可讓音訊和視訊通話支援的虛擬化技術。 此擴充[Microsoft Lync 2010 中的用戶端虛擬化](https://go.microsoft.com/fwlink/?linkid=330447)本白皮書中所述的 Microsoft Lync Server 2010 功能。 符合標準電話法規、 規範支援 E911 是也包含在內。 下列各節說明 Lync VDI 外掛程式已知的功能會受到限制所支援的虛擬化技術。

<div>

## <a name="support-for-virtualization-technologies"></a>對虛擬化技術的支援

Lync VDI 外掛程式可支援完整桌面 remoting 在個人虛擬桌面案例中，但不是在遠端桌面工作階段的案例。 這些案例說明如下：

  - **支援： 個人化的虛擬桌面或虛擬桌面基礎結構 (VDI)。**   在此案例中，每位使用者登入可自訂的虛擬桌面，而且能夠儲存在桌面上會保存跨工作階段的檔案。 Microsoft 遠端桌面服務、 VMware 水平線檢視，以及 Citrix XenDesktop 是經過測試與 Lync 搭配使用的實作。 供應商特有 VDI 環境和 microsoft 經過測試的用戶端硬體的相關資訊，請參閱[Microsoft lync 合格基礎結構](https://go.microsoft.com/fwlink/?linkid=313435)。

  - **不支援： 遠端桌面工作階段。**   在此案例中，每個使用者用來登入的一般虛擬桌面工作階段無法自訂。 範例實作包括 Microsoft 遠端桌面工作階段 (RDSH)，以及 Citrix XenApp 結合 Citrix 收件者。

Lync VDI 外掛程式不支援其他虛擬化技術，例如應用程式虛擬化，而不需要安裝完整的應用程式在本機上允許使用應用程式。 範例實作包含 Citrix XenApp 和 Microsoft Application Virtualization (APP-V)。 不支援應用程式資料流、 應用程式遠端處理和混合式虛擬化模式 （例如，應用程式遠端處理的完整桌面的遠端處理）。

若要允許擴充性，Lync VDI 外掛程式的設計目的在於使用獨立平台的 Api 呼叫動態虛擬通道 (DVCs)。 Lync 不明確支援的案例，請參閱支援從 VDI 解決方案提供者的陳述式。

</div>

<div>

## <a name="known-feature-limitations"></a>已知的功能會受到限制

下面是已知限制在 VDI 環境中使用 Lync 2013 時：

  - 沒有有限的支援通話委派與回應群組代理人匿名功能。

  - 不支援以下功能：
    
      - 整合式音訊裝置及視訊裝置調整頁面。
    
      - 多重檢視視訊。
    
      - 錄製交談。
    
      - 遠端桌面服務 (RDS)。
    
      - 加入會議匿名 （也就加入與您的組織不同盟的組織所主控的 Lync 會議）。
    
      - 使用 Lync VDI 外掛程式以及 Lync Phone Edition 裝置。
    
      - 在網路中斷連線的情況下延續通話。
    
      - 自訂等候鈴聲及音樂上保留功能。

  - 在 Office 365 環境中不支援 Lync VDI 外掛程式。

</div>

</div>

<span> </span>

</div>

</div>

</div>

