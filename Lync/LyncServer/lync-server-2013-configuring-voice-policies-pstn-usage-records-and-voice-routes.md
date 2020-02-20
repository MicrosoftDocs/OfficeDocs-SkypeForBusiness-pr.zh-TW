---
title: 設定語音原則、 PSTN 使用方式記錄和語音路由
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring voice policies, PSTN usage records, and voice routes
ms:assetid: 1e5a15f9-6f42-4dc6-baaa-24daf54afc4d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398272(v=OCS.15)
ms:contentKeyID: 48183573
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e8fbaa4d6c5855ec1c94e4eeca0b2cb5acaaa914
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154105"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-voice-policies-pstn-usage-records-and-voice-routes-in-lync-server-2013"></a>在 Lync Server 2013 中設定語音原則、 PSTN 使用方式記錄和語音路由

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-10_

語音原則、PSTN 使用方式記錄和語音路由密切相關。您可以選取一組撥號功能，接著指派一組 PSTN 使用方式記錄給原則，以便指定獲指派語音原則的使用者或群組可獲得哪些權限授權，如此就能設定語音原則。語音路由也會被指派 PSTN 使用方式記錄，這些記錄會用來比對路由與獲授權使用這些路由的使用者。也就是說，使用者可以撥打的電話，只限於使用他們有相符 PSTN 使用方式記錄之路由的電話。

新 Enterprise Voice 部署的建議工作流程是：從設定包含適當 PSTN 使用方式記錄的語音原則開始，接著將適當路由關聯給每個 PSTN 使用方式記錄。

<div>


> [!NOTE]
> 您也可以在「<EM>使用者</EM>」範圍建立語音原則，然後將其指派給個別使用者或群組。



</div>

如需執行每項工作的詳細步驟，請參閱本節程序。

<div>

## <a name="in-this-section"></a>本章節內容

  - [設定語音原則和 PSTN 使用方式記錄，以授權撥號功能及 Lync Server 2013 中的權限](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)

  - [Lync Server 2013 中檢視 PSTN 使用方式記錄](lync-server-2013-view-pstn-usage-records.md)

  - [在 Lync Server 2013 中設定撥出電話的語音路由](lync-server-2013-configuring-voice-routes-for-outbound-calls.md)

  - [匯出及匯入 Lync Server 2013 中的語音路由設定](lync-server-2013-exporting-and-importing-voice-routing-configuration.md)

  - [暫止的變更語音路由設定 Lync Server 2013 中發佈](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)

  - [測試 Lync Server 2013 中的語音路由](lync-server-2013-test-voice-routing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

