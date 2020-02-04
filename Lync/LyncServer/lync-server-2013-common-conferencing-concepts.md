---
title: Lync Server 2013：常見的會議概念
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Common conferencing concepts
ms:assetid: a21d4987-1c0a-44c8-8a39-9c17ffb57f3c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688158(v=OCS.15)
ms:contentKeyID: 49733762
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 91d21526cfcd6d2c78cd67660136e8f7600d1841
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742773"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="common-conferencing-concepts-in-lync-server-2013"></a>Lync Server 2013 中的常見會議概念

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-19_

所有類型的會議共有幾個概念。 以下各節將說明這些步驟。

<div>

## <a name="policies-and-bandwidth-management"></a>原則與頻寬管理

Lync Server 2013 可讓系統管理員針對使用者可以組織的會議類型設定原則。 這可協助您強制實施貴組織的原則並控制頻寬使用量。 您可以定義各種會議原則，並將他們指派給個別的使用者和使用者群組。 您也可以設定控制對等交談的原則。 如需設定會議原則的詳細資訊，請參閱作業檔中的[Lync Server 2013 中的會議原則](lync-server-2013-conferencing-policies.md)。 如需頻寬管理的詳細資料，請參閱[Lync server 2013 中的通話許可控制概覽](lync-server-2013-overview-of-call-admission-control.md)，以及[在 lync server 2013 中設定影片頻寬](lync-server-2013-configuring-video-bandwidth.md)。

</div>

<div>

## <a name="archiving-and-compliance-features"></a>封存與合規性功能

如果您的組織必須遵循合規性規範，Lync Server 2013 提供您可以使用的功能。 您可以使用存檔功能來封存會議中呈現的內容，以及立即訊息（IM）交談和 IM 會議的內容。 如需詳細資訊，請參閱規劃檔中的[Lync Server 2013 中的存檔規劃](lync-server-2013-planning-for-archiving.md)。 您可以使用 Persistent 聊天伺服器的相容性功能，來封存一段時間內保留的多方或主題式交談。 如需詳細資訊，請參閱規劃檔中的[Lync server 2013 中的持續聊天伺服器規劃](lync-server-2013-planning-for-persistent-chat-server.md)。

</div>

<div>

## <a name="monitoring-feature"></a>[監視] 功能

[監視伺服器] 功能可以捕獲通話詳細資料記錄（CDRs），您可以使用這些記錄來追蹤哪些使用者與使用 Lync Server 2013 的其他使用者交談。 如需有關部署和設定監視的詳細資料，請參閱[在 Lync Server 2013 中部署監視](lync-server-2013-deploying-monitoring.md)。

</div>

<div>

## <a name="enabling-external-participation-in-conferences"></a>在會議中啟用外部參與

您可以讓外部使用者也能在受邀者參與會議時，在 Lync Server 2013 會議中大幅增加投資的好處。 外部使用者可以包括：

  - ****    如果您組織的使用者是在您的防火牆外工作，且正在使用其膝上型電腦或其他 Lync Server 2013 裝置，則您組織的遠端使用者就是自己的使用者。

  - **同盟使用者**   與公司合作的使用者，您可與其他人同時執行 Lync Server 2013。 若要讓您的使用者能夠輕鬆地與這些使用者聯繫，您可以建立與這些公司的聯盟關聯。

  - **匿名使用者**   由您的使用者專門邀請之加入特定會議的任何其他外部使用者。 貴公司中的會議召集人可以傳送電子郵件給外部使用者的會議邀請。 電子郵件包含外部使用者可以按一下以加入會議的連結。

若要啟用任何一種或所有案例，您必須部署邊緣伺服器，以協助您在 Lync Server 2013 部署與外部使用者之間進行安全通訊。 使用 Edge 伺服器的 Lync Server 2013 解決方案比其他解決方案（例如虛擬私人網路（VPN））提供較高的品質。 如需詳細資訊，請參閱[在 Lync Server 2013 中規劃外部使用者存取](lync-server-2013-planning-for-external-user-access.md)。

此外，無論您是否部署邊緣伺服器，您都可以讓使用者（無論是組織內部或外部）從標準 PSTN 手機撥入，以加入內部部署的音訊會議。 這是透過部署 Lync Server 2013 電話撥入式會議來完成。

</div>

<div>

## <a name="compatibility-among-meeting-types-and-client-versions"></a>會議類型與用戶端版本之間的相容性

如果您要讓 Lync Server 2013 與舊版 Office 通訊伺服器及其用戶端互動，您必須注意下列問題：

  - 使用 Lync Server 2013 的使用者無法排程 Live Meeting 會議，或修改此類型的任何已遷移會議。

  - 使用 Lync Server 2013 的使用者必須在運行 Office 通訊伺服器 2007 R2 的伺服器上安裝 live Meeting 會議（除了 Lync Server 2013 之外），才能參與這些會議。

  - 當 Live Meeting 會議遷移至 Lync Server 2013 時，會議內容不會遷移。 如果需要此內容，必須再次上傳它。

</div>

</div>

<span> </span>

</div>

</div>

</div>

