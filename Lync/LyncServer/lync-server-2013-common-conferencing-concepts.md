---
title: Lync Server 2013：一般會議概念
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
ms.openlocfilehash: d2afd309f59a66a7117d43b930500a7807d493d1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190936"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="common-conferencing-concepts-in-lync-server-2013"></a>Lync Server 2013 的常見會議概念

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-19_

所有會議類型一般都有數個概念。 以下各節將說明這些內容。

<div>

## <a name="policies-and-bandwidth-management"></a>原則與頻寬管理

Lync Server 2013 可讓系統管理員設定使用者可以組織之會議類型的原則。 這可協助您強制執行組織的原則及控制頻寬使用量。 您可以定義各種各樣的會議原則，並將它們指派給個別使用者和使用者群組。 您也可以設定管理對等交談的原則。 如需設定會議原則的詳細資訊，請參閱 Operations 檔中的[Lync Server 2013 中的會議原則](lync-server-2013-conferencing-policies.md)。 如需頻寬管理的詳細資訊，請參閱[lync server 2013 中的通話許可控制](lync-server-2013-overview-of-call-admission-control.md)與在[lync server 2013 中設定影片頻寬](lync-server-2013-configuring-video-bandwidth.md)的概述。

</div>

<div>

## <a name="archiving-and-compliance-features"></a>封存和合規性功能

當您的組織必須遵循法規遵從性規定時，Lync Server 2013 提供您可以使用的功能。 您可以使用封存功能來封存會議中所提供的內容，也可以使用立即訊息 (IM) 交談和 IM 會議的內容。 如需詳細資訊，請參閱規劃檔中的[規劃 Lync Server 2013 中的](lync-server-2013-planning-for-archiving.md)封存。 您可以使用 Persistent Chat Server 的符合性功能，封存隨時間保留的多方、主題型交談。 如需詳細資訊，請參閱規劃檔中的在[Lync server 2013 中規劃 Persistent Chat Server](lync-server-2013-planning-for-persistent-chat-server.md) 。

</div>

<div>

## <a name="monitoring-feature"></a>監控功能

監控伺服器功能可 (Cdr) 中捕獲詳細通話記錄，您可以用來追蹤哪些使用者與使用 Lync Server 2013 的其他使用者交談。 如需部署及設定監視的詳細資訊，請參閱[在 Lync Server 2013 中部署監控](lync-server-2013-deploying-monitoring.md)。

</div>

<div>

## <a name="enabling-external-participation-in-conferences"></a>啟用會議的外部參加功能

您可以讓外部使用者也可以在邀請時參與會議，以大幅提高在 Lync Server 2013 會議中投資的效益。 外部使用者包括：

  - **遠端使用者**    組織本身的使用者，當他們在防火牆外工作時使用其膝上型電腦或其他 Lync Server 2013 裝置。

  - 同盟**使用者**    與同時執行 Lync Server 2013 之公司有關的使用者。 為了方便您的使用者輕鬆連絡這些使用者，您可以和這些公司建立同盟關係。

  - **匿名使用者**    由您的使用者特別邀請您加入特定會議的任何其他外部使用者。 公司裡的會議召集人可以將會議的電子郵件邀請寄送給外部使用者。 該電子郵件內含一則連結，外部使用者只需要點選一下即可加入會議。

若要啟用任何或所有上述案例，您必須部署 Edge Server，以協助您啟用 Lync Server 2013 部署和外部使用者之間的安全通訊。 使用 Edge Server 的 Lync Server 2013 解決方案比其他解決方案（如虛擬私人網路 (VPN) ）提供更高品質的媒體。 如需詳細資訊，請參閱[在 Lync Server 2013 中規劃外部使用者存取](lync-server-2013-planning-for-external-user-access.md)。

此外，不論是否部署 Edge Server，您也可以讓使用者 (，也就是組織內部或外部的使用者) 從標準 PSTN 電話撥入以加入內部部署音訊會議。 這是透過部署 Lync Server 2013 電話撥入式會議來完成。

</div>

<div>

## <a name="compatibility-among-meeting-types-and-client-versions"></a>會議類型與用戶端版本的相容性

如果您要讓 Lync Server 2013 與舊版 Office 通訊伺服器及其用戶端互動，您必須注意下列問題：

  - 使用 Lync Server 2013 的使用者無法排程 Live Meeting 會議，或是修改任何此類型的已遷移會議。

  - 使用 Lync Server 2013 的使用者必須在電腦2007上安裝 live Meeting 會議，而該會議必須安裝在其電腦上的 Live meeting 會議 (，除了 Lync Server 2013) 之外，還必須在電腦上安裝 Live meeting 用戶端，才能參加這些會議。

  - 當 Live Meeting 會議遷移至 Lync Server 2013 時，不會遷移會議內容。 若是此時需要這些內容，就必須重新上傳。

</div>

</div>

<span> </span>

</div>

</div>

</div>

