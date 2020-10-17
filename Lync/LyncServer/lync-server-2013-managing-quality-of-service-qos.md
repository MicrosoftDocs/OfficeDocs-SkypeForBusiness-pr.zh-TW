---
title: 'Lync Server 2013：管理服務品質 (QoS) '
description: Lync Server 2013：管理服務品質 (QoS) 。
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
ms.openlocfilehash: df0e84389cc030cd63fe04c46929bd981a074aec
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552719"
---
# <a name="managing-quality-of-service-qos-in-lync-server-2013"></a>在 Lync Server 2013 中管理服務品質 (QoS) 

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-11-07_

服務品質 (QoS) 是某些組織所用的網路技術，可協助提供最佳的音訊和視頻通訊使用者體驗。 QoS 最常用於頻寬有限的網路：有大量網路資料包會爭用相對的可用頻寬量，服務品質可為系統管理員提供一種方法，讓系統管理員可以將較高優先順序指派給攜帶音訊或視頻資料的封包。 透過將這些封包以較高優先順序傳送，音訊和影片通訊的速度可能會更快，且中斷較低，其方式就是檔案傳輸、網頁流覽或資料庫備份等相關的網路會話。 這是因為用於進行檔案傳輸或資料庫備份的網路封包是以「最大努力」優先順序指派。

<div>


> [!NOTE]  
> 一般來說，服務品質只適用于內部網路上的通訊會話。 當您執行 QoS 時，會設定您的伺服器和路由器以支援封包標記;不過，您可以設定這些裝置以特定方式支援封包標記。 您無法假定在網際網路或其他網路上都支援服務品質。 即使其他網路上支援品質的服務，也無法保證 QoS 會以您在網路上設定服務的相同方式來設定。



</div>

Microsoft Lync Server 2013 不需要服務品質;如果您目前未使用 QoS 您不需要在安裝 Lync Server 2013 之前安裝服務。 如果您的網路上有大量的封包遺失，建議的方法是緩解此問題，以增加額外的頻寬。 如果無法新增更多的頻寬，您可能想要改為執行服務品質。

Lync Server 2013 為服務品質提供完整支援：這表示已使用 QoS 的組織可以輕鬆地將 Lync Server 整合至現有的網路基礎結構。 為了達到此目的，您必須執行下列工作：

  - [為不是以 Windows 為基礎的裝置啟用 Lync Server 2013 中的 QoS](lync-server-2013-enabling-qos-for-devices-that-are-not-based-on-windows.md)。 根據預設，系統會停用電腦及其他裝置的 QoS，例如執行其他作業系統的 Iphone) 等 (。 雖然您可以使用 Lync Server 來啟用及停用裝置的服務品質，但通常無法使用產品修改這些裝置所使用的 DSCP 代碼。

  - [針對會議、應用程式及轉送伺服器，在 Lync Server 2013 中設定埠範圍](lync-server-2013-configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md)。 您必須為不同的封包類型（如音訊和影片）預約一組獨特的埠。 透過 Lync Server 2013，您未啟用或停用服務品質，例如，將屬性值設定為 True 或 False。 相反地，您可以設定埠範圍，然後建立及套用群組原則，以啟用服務品質。 如果您稍後決定不使用 QoS 您只要移除適當的群組原則物件，就可以「停用」服務品質。

  - [在 Lync Server 2013 中設定 Edge server 的埠範圍](lync-server-2013-configuring-port-ranges-for-your-edge-servers.md)。 您可以將 Edge server 設定成使用與其他伺服器相同的埠範圍，但這不是必要的。

  - [在 Lync Server 2013 中設定 Microsoft Lync 用戶端的埠範圍](lync-server-2013-configuring-port-ranges-for-your-microsoft-lync-clients.md)。 這些埠範圍只適用于用戶端電腦，通常與伺服器上設定的埠範圍不同。

  - [針對會議、應用程式及轉送伺服器，在 Lync Server 2013 中設定服務品質原則](lync-server-2013-configuring-a-quality-of-service-policy-for-your-conferencing-application-and-mediation-servers.md)。 這些原則決定適用于不同的資料包類型的 DSCP 代碼。

  - [在 Lync Server 2013 中為您的 A/V Edge server 設定品質服務原則](lync-server-2013-configuring-a-quality-of-service-policy-for-your-a-v-edge-servers.md)。 這只應該針對 Edge server 的內部端進行。 這是因為服務品質已設計為用於內部網路，而不是在網際網路上。

  - [針對在 windows 7 或 windows 8 上執行的用戶端，在 Lync Server 2013 中設定服務品質原則](lync-server-2013-configuring-quality-of-service-policies-for-clients-running-on-windows-7-or-windows-8.md)。 請注意，Microsoft Lync Server 2013 不支援其他 Windows 作業系統（如 Windows Vista 或 Windows XP）的 QoS。

  - [在 Lync Server 2013 中設定 Microsoft Lync Phone Edition 裝置上的服務品質](lync-server-2013-configuring-quality-of-service-on-microsoft-lync-phone-edition-devices.md)。 根據預設，Lync Phone Edition 裝置會啟用 QoS。 不過，您可能會想要變更預設 DSCP 值，以確保組織中的所有音訊封包都使用相同的 DSCP 碼。

<div>


> [!NOTE]  
> 如果您使用的是 Microsoft Windows Server 2012 或 Windows Server 2012 R2，您可能會對一組新的 Windows PowerShell Cmdlet 感興趣，以在該平臺上管理服務品質。 如需詳細資訊，請參閱 Windows PowerShell 中的網路服務指令程式品質 Cmdlet [https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps](https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps) 。



</div>

</div>

<span> </span>

</div>

</div>

</div>

