---
title: Lync Server 2013： 規範取代 XmlAdapter 以自訂常設聊天室伺服器規範配接器
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
ms.openlocfilehash: 5c6cd49ee2596627849b5b67147d6f7ef2a328e3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050865"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="replacing-the-xmladapter-with-a-customized-persistent-chat-server-compliance-adapter-in-lync-server-2013"></a>使用 Lync Server 2013 中的自訂常設聊天室伺服器規範介面卡規範取代 XmlAdapter

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-11-01_

您可以撰寫自訂的介面卡，而不是使用隨 Persistent Chat Server XmlAdapter。 若要完成此工作，您必須提供包含公用類別 (實作了 **IComplianceAdapter** 介面) 的 .NET Framework 組件。 Persistent Chat Server 集區中，您必須在每一部伺服器的 Persistent Chat Server 安裝資料夾中放置這個組件。 所有符合此規範的伺服器皆可提供規範資料給您的配接器，但規範伺服器不會提供重複的規範資料給您配接器的多個執行個體。

<div>

## <a name="implementing-the-icomplianceadapter-interface"></a>實作 IComplianceAdapter 介面

Compliance.dll 組件中的命名空間中定義介面`Microsoft.Rtc.Internal.Chat.Server.Compliance`。 此介面定義了您自訂介面卡必須實作的兩種方法。

    void SetConfig(AdapterConfig config)

常設聊天室規範伺服器就會呼叫此方法，配接器第一次載入時。 `AdapterConfig`包含相關規範配接器的常設聊天室規範組態。

    void Translate(ConversationCollection conversations)

常設聊天室規範伺服器會定期呼叫此方法，只要沒有要翻譯的新資料。 這段時間間隔相當`RunInterval`，常設聊天室規範組態設定。

`ConversationCollection`包含的上次呼叫此方法時所收集的交談資訊。

</div>

</div>

<span> </span>

</div>

</div>

</div>

