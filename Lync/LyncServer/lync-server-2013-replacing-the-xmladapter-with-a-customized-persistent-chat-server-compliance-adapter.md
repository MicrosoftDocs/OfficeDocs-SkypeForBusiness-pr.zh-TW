---
title: Lync Server 2013：以自訂 Persistent Chat Server 相容性配接器取代 XmlAdapter
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Replacing the XmlAdapter with a customized Persistent Chat Server Compliance adapter
ms:assetid: 2cb70db2-663f-40a6-abcf-89ea7d4a8b65
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ680106(v=OCS.15)
ms:contentKeyID: 49558152
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c90452edc96a424111fcaa8c99dcf60e55e0109
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536350"
---
# <a name="replacing-the-xmladapter-with-a-customized-persistent-chat-server-compliance-adapter-in-lync-server-2013"></a>以 Lync Server 2013 中的自訂 Persistent Chat Server 相容性配接器取代 XmlAdapter

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

您可以撰寫自訂介面卡，而不是使用隨 Persistent Chat Server 安裝的 XmlAdapter。 若要完成此工作，您必須提供包含公用類別 (實作了 **IComplianceAdapter** 介面) 的 .NET Framework 組件。 您必須將此元件放在 Persistent Chat Server 集區中每一部伺服器的 Persistent Chat Server 安裝資料夾中。 所有符合此規範的伺服器皆可提供規範資料給您的配接器，但規範伺服器不會提供重複的規範資料給您配接器的多個執行個體。

<div>

## <a name="implementing-the-icomplianceadapter-interface"></a>實現 IComplianceAdapter 介面

該介面是在命名空間的 Compliance.dll 元件中定義的 `Microsoft.Rtc.Internal.Chat.Server.Compliance` 。 此介面定義了您自訂介面卡必須實作的兩種方法。

    void SetConfig(AdapterConfig config)

當配接器第一次載入時，Persistent Chat 規範伺服器會呼叫此方法。 `AdapterConfig`包含與規範介面卡相關的 Persistent Chat 相容性設定。

    void Translate(ConversationCollection conversations)

只要有要翻譯的新資料，Persistent Chat 規範伺服器便會定期呼叫此方法。 此時間間隔相當於 `RunInterval` 持續性聊天規範設定中的設定。

`ConversationCollection`包含上次呼叫此方法時所收集到的交談資訊。

</div>

</div>

<span> </span>

</div>

</div>

</div>

