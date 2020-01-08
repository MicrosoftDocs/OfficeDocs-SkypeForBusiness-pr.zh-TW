---
title: Lync Server 2013：以自訂的永久性聊天伺服器合規性配接器取代 XmlAdapter
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Replacing the XmlAdapter with a customized Persistent Chat Server Compliance adapter
ms:assetid: 2cb70db2-663f-40a6-abcf-89ea7d4a8b65
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ680106(v=OCS.15)
ms:contentKeyID: 49558152
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3d26e470438dc8a79dbaa3944c05ad4158cafe44
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975473"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="replacing-the-xmladapter-with-a-customized-persistent-chat-server-compliance-adapter-in-lync-server-2013"></a>在 Lync Server 2013 中使用自訂的持續聊天伺服器合規性配接器來取代 XmlAdapter

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

您可以撰寫自訂配接器，而不是使用隨持續聊天伺服器一起安裝的 XmlAdapter。 若要完成這項作業，您必須提供包含實現**IComplianceAdapter**介面之公用類別的 .net Framework 元件。 您必須將此元件放在持續聊天伺服器池中每個伺服器的 [永久聊天伺服器安裝] 資料夾中。 任何一個合規性伺服器都可以為您的配接器提供合規性資料，但合規性伺服器將不會提供重複的合規性資料給您的配接器的多個實例。

<div>

## <a name="implementing-the-icomplianceadapter-interface"></a>實現 IComplianceAdapter 介面

介面是在命名空間`Microsoft.Rtc.Internal.Chat.Server.Compliance`的合規性 .dll 程式集中定義。 介面定義您的自訂配接器必須實現的兩種方法。

    void SetConfig(AdapterConfig config)

在配接器第一次載入時會呼叫此方法。 `AdapterConfig`包含與合規性配接器相關的持續聊天相容性設定。

    void Translate(ConversationCollection conversations)

只要有要翻譯的新資料，持續性聊天規範伺服器就會以週期性的間隔呼叫此方法。 此時間間隔等於在持續聊天`RunInterval`相容性設定中設定的。

`ConversationCollection`包含上次呼叫此方法時所收集的交談資訊。

</div>

</div>

<span> </span>

</div>

</div>

</div>

