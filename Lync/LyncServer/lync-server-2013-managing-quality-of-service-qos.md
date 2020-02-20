---
title: Lync Server 2013： 管理服務的品質 (QoS)
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
ms.openlocfilehash: b72fbd1275060ce01d56cb64e11cdd27f38b2e54
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150184"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-quality-of-service-qos-in-lync-server-2013"></a>管理服務的品質 (QoS 在 Lync Server 2013)

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-11-07_

服務品質 (QoS) 是一種網路技術，在某些組織中用於協助提供最佳使用者經驗的音訊及視訊通訊。 QoS 最常用於網路頻寬所在有限： 設立了許多網路封包競用相當少量的可用頻寬，Quality of Service 提供讓系統管理員指派給封包的較高的優先順序持有音訊或視訊資料。 授與這些封包優先順序較高，音訊和視訊通訊未經過可能會完成速度更快，並使用較少的中斷，比涉及之類的檔案傳輸、 網站瀏覽]，或資料庫備份的網路工作階段。 這是因為用於檔案傳輸或資料庫備份的網路封包指派 「 最佳投入比 」 的優先順序。

<div>


> [!NOTE]  
> 一般而言，Quality of Service 僅適用於您的內部網路上的通訊工作階段。 當您實作 QoS 時，設定您的伺服器和路由器，以支援封包標示;不過，您設定這些裝置所支援封包標示以特定方式。 您不能假定其他網路或網際網路上，將支援的服務品質。 即使品質服務支援其他網路上是否有不保證能 QoS 設定您網路上設定服務的方式相同。



</div>

Microsoft Lync Server 2013 不需要的服務品質;如果您目前未使用 QoS，沒有安裝 Lync Server 2013 之前先安裝服務的需求。 如果您遇到相當可觀的封包遺失在您的網路以避免此問題的建議方式是將新增額外的頻寬。 如果新增更多的頻寬不可行，您可能想要改為實作的服務品質。

Lync Server 2013 提供的服務品質的完整支援:，表示已經在使用 QoS 的組織可以輕鬆地將 Lync Server 整合到其現有的網路基礎結構。 若要這麼做，您必須執行下列工作：

  - [裝置不採用 Windows 的 Lync Server 2013 中啟用 QoS](lync-server-2013-enabling-qos-for-devices-that-are-not-based-on-windows.md)。 根據預設，QoS 已停用的電腦及其他裝置 （例如 Iphone) 執行其他的作業系統。 雖然您可以使用 Lync Server 來啟用及停用裝置的服務品質，您通常無法使用產品來修改這些裝置所用的 DSCP 代碼。

  - [設定會議、 應用程式及中繼伺服器的 Lync Server 2013 中的連接埠範圍](lync-server-2013-configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md)。 您必須保留一組唯一不同的封包類型，例如音訊和視訊的連接埠。 搭配 Lync Server 2013 您不要未啟用或停用服務品質，說，屬性值設定為 True 或 False。 相反地，您會藉由設定連接埠範圍然後建立並套用群組原則啟用的服務品質。 如果您稍後決定不應使用 QoS 您可以 「 停用 「 服務品質只移除適當的群組原則物件。

  - [設定 Lync Server 2013 Edge Server 的連接埠範圍](lync-server-2013-configuring-port-ranges-for-your-edge-servers.md)。 雖然並非必要，您可以設定您的 Edge server 使用相同的連接埠範圍作為其他的伺服器。

  - [設定您的 Microsoft Lync 用戶端，Lync Server 2013 中的連接埠範圍](lync-server-2013-configuring-port-ranges-for-your-microsoft-lync-clients.md)。 這些連接埠範圍僅適用於用戶端電腦和通常不是在您的伺服器上設定的連接埠範圍相同。

  - [設定會議、 應用程式及中繼伺服器的 Lync Server 2013 中的服務品質原則](lync-server-2013-configuring-a-quality-of-service-policy-for-your-conferencing-application-and-mediation-servers.md)。 這些原則決定套用至不同的封包類型的 DSCP 代碼。

  - [設定服務品質原則的 A / V Edge Server 在 Lync Server 2013 中](lync-server-2013-configuring-a-quality-of-service-policy-for-your-a-v-edge-servers.md)。 這只應為您的 Edge server 之對內端。 這是因為 Quality of Service 設計用於您的內部網路上並不是在網際網路上。

  - [在 Windows 7 或 Windows 8 上執行的用戶端的 Lync Server 2013 中設定服務品質原則](lync-server-2013-configuring-quality-of-service-policies-for-clients-running-on-windows-7-or-windows-8.md)。 請注意，Microsoft Lync Server 2013 不支援 QoS 適用於其他 Windows 作業系統，例如 Windows Vista 或 Windows XP。

  - [設定服務品質 Lync Server 2013 中的 Microsoft Lync Phone Edition 裝置上](lync-server-2013-configuring-quality-of-service-on-microsoft-lync-phone-edition-devices.md)。 根據預設，QoS 已啟用 Lync Phone Edition 裝置。 不過，您可能想要變更預設的 DSCP 值，以確保組織中的所有音訊封包都使用相同的 DSCP 程式碼。

<div>


> [!NOTE]  
> 如果您使用 Microsoft Windows Server 2012 或 Windows Server 2012 R2 您可能會感興趣一組新的 Windows PowerShell cmdlet 可用於管理該平台上的服務品質。 如需詳細資訊，請參閱網路品質的服務中的指令程式在 Windows PowerShell [https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps](https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps)。



</div>

</div>

<span> </span>

</div>

</div>

</div>

