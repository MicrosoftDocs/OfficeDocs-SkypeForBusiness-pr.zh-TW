---
title: Lync Server 2013：管理服務品質（QoS）
ms.reviewer: ''
f1.keywords:
- NOCSH
TOCTitle: Managing Quality of Service (QoS)
author: lanachin
ms.author: v-lanac
ms.manager: serdars
ms:assetid: ab1051c3-8380-4d72-86df-37a61b1e4a41
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg405409(v=OCS.15)
ms:contentKeyID: 48185049
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce88471361c63fde3ebf8a3ea716a140567e722e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725583"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-quality-of-service-qos-in-lync-server-2013"></a>管理 Lync Server 2013 中的服務品質（QoS）

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-11-07_

服務品質（QoS）是一些組織所用的網路技術，可協助提供最佳的音訊和視頻通訊使用者體驗。 QoS 最常用於頻寬有限的網路上：有大量網路資料包爭用相對較少的可用頻寬，服務品質會提供一種方式，讓管理員指派較高優先順序至資料包攜帶音訊或視頻資料。 透過將這些資料包設為較高的優先順序，音訊與視頻通訊可能會更快且中斷較少，因為涉及檔案傳輸、網頁流覽或資料庫備份等操作的網路會話。 這是因為用於檔案傳輸或資料庫備份的網路資料包已獲指派「最大努力」的優先順序。

<div>


> [!NOTE]  
> 一般來說，服務品質只適用于內部網路上的通訊會話。 當您實現 QoS 時，請將您的伺服器和路由器設定為支援資料包標記;不過，您可以將這些裝置設定為支援以特定方式進行資料包標記。 您無法假設在網際網路或其他網路上不支援該服務品質。 即使在其他網路上支援 Quality Services，也不會保證 QoS 的設定方式與您在網路上設定服務的方式相同。



</div>

Microsoft Lync Server 2013 不需要服務品質;如果您目前未使用 QoS，就不需要在安裝 Lync Server 2013 之前安裝該服務。 如果您在網路上遇到大量的資料包遺失，建議的方式就是緩解這個問題，就是要增加額外的頻寬。 如果不可能增加更多頻寬，您可能會想要改為執行服務品質。

Lync Server 2013 提供完整的服務品質支援：這表示已使用 QoS 的組織可以輕鬆地將 Lync Server 整合至其現有的網路基礎結構。 若要這樣做，您必須執行下列工作：

  - [在 Lync Server 2013 中針對不是以 Windows 為基礎的裝置啟用 QoS](lync-server-2013-enabling-qos-for-devices-that-are-not-based-on-windows.md)。 根據預設，系統會針對執行其他作業系統的電腦和其他裝置（例如 Iphone）停用 QoS。 雖然您可以使用 Lync Server 來啟用和停用裝置的服務品質，但您通常無法使用該產品來修改這些裝置所使用的 DSCP 代碼。

  - [針對您的會議、應用程式及中繼伺服器，在 Lync Server 2013 中設定埠範圍](lync-server-2013-configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md)。 您必須為不同的資料包類型（例如音訊和影片）保留一組獨特的埠。 使用 Lync Server 2013，您不可以啟用或停用服務品質，比如說將屬性值設定為 True 或 False。 相反地，您必須先設定埠範圍，然後建立並套用群組原則，才能啟用服務品質。 如果您稍後決定不使用 QoS，您只要移除適當的群組原則物件，就可以「停用」服務品質。

  - [在 Lync Server 2013 中設定邊緣伺服器的埠範圍](lync-server-2013-configuring-port-ranges-for-your-edge-servers.md)。 雖然不必要，但您可以將邊緣伺服器設定為使用與其他伺服器相同的埠範圍。

  - [在 Lync Server 2013 中為您的 Microsoft Lync 用戶端設定埠範圍](lync-server-2013-configuring-port-ranges-for-your-microsoft-lync-clients.md)。 這些埠範圍只適用于用戶端電腦，且通常與您伺服器上設定的埠範圍不同。

  - [針對您的會議、應用程式及中繼伺服器，在 Lync Server 2013 中設定品質服務原則](lync-server-2013-configuring-a-quality-of-service-policy-for-your-conferencing-application-and-mediation-servers.md)。 這些原則會判斷套用到不同資料包類型的 DSCP 代碼。

  - [在 Lync Server 2013 中設定您的 a/V 邊緣伺服器的服務品質原則](lync-server-2013-configuring-a-quality-of-service-policy-for-your-a-v-edge-servers.md)。 只能針對邊緣伺服器的內部端執行此動作。 那是因為服務品質是專為在您的內部網路（而不是在網際網路）上使用而設計。

  - [針對在 windows 7 或 windows 8 上執行的用戶端，在 Lync Server 2013 中設定服務品質原則](lync-server-2013-configuring-quality-of-service-policies-for-clients-running-on-windows-7-or-windows-8.md)。 請注意，Microsoft Lync Server 2013 不支援其他 Windows 作業系統（例如 Windows Vista 或 Windows XP）的 QoS。

  - [在 Lync Server 2013 中設定 Microsoft Lync Phone Edition 裝置上的服務品質](lync-server-2013-configuring-quality-of-service-on-microsoft-lync-phone-edition-devices.md)。 根據預設，Lync 手機版裝置會啟用 QoS 功能。 不過，您可能會想要變更預設 DSCP 值，以確保貴組織中的所有音訊資料包都使用相同的 DSCP 代碼。

<div>


> [!NOTE]  
> 如果您使用的是 Microsoft Windows Server 2012 或 Windows Server 2012 R2，您可能會想要在該平臺上管理服務品質所用的一組新的 Windows PowerShell Cmdlet。 如需詳細資訊，請參閱 Windows PowerShell 中的網路服務品質[https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps](https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps)Cmdlet。



</div>

</div>

<span> </span>

</div>

</div>

</div>

