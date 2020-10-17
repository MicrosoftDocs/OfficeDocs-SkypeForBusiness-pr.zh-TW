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
# <a name="replacing-the-xmladapter-with-a-customized-persistent-chat-server-compliance-adapter-in-lync-server-2013"></a><span data-ttu-id="4e22b-102">以 Lync Server 2013 中的自訂 Persistent Chat Server 相容性配接器取代 XmlAdapter</span><span class="sxs-lookup"><span data-stu-id="4e22b-102">Replacing the XmlAdapter with a customized Persistent Chat Server Compliance adapter in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4e22b-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="4e22b-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="4e22b-104">您可以撰寫自訂介面卡，而不是使用隨 Persistent Chat Server 安裝的 XmlAdapter。</span><span class="sxs-lookup"><span data-stu-id="4e22b-104">You can write a custom adapter instead of using the XmlAdapter that is installed with Persistent Chat Server.</span></span> <span data-ttu-id="4e22b-105">若要完成此工作，您必須提供包含公用類別 (實作了 **IComplianceAdapter** 介面) 的 .NET Framework 組件。</span><span class="sxs-lookup"><span data-stu-id="4e22b-105">To accomplish this, you must provide a .NET Framework assembly that contains a public class that implements the **IComplianceAdapter** interface.</span></span> <span data-ttu-id="4e22b-106">您必須將此元件放在 Persistent Chat Server 集區中每一部伺服器的 Persistent Chat Server 安裝資料夾中。</span><span class="sxs-lookup"><span data-stu-id="4e22b-106">You must place this assembly in the Persistent Chat Server installation folder of each server in your Persistent Chat Server pool.</span></span> <span data-ttu-id="4e22b-107">所有符合此規範的伺服器皆可提供規範資料給您的配接器，但規範伺服器不會提供重複的規範資料給您配接器的多個執行個體。</span><span class="sxs-lookup"><span data-stu-id="4e22b-107">Any one of the Compliance servers can provide compliance data to your adapter, but the compliance servers will not provide duplicate compliance data to multiple instances of your adapter.</span></span>

<div>

## <a name="implementing-the-icomplianceadapter-interface"></a><span data-ttu-id="4e22b-108">實現 IComplianceAdapter 介面</span><span class="sxs-lookup"><span data-stu-id="4e22b-108">Implementing the IComplianceAdapter interface</span></span>

<span data-ttu-id="4e22b-109">該介面是在命名空間的 Compliance.dll 元件中定義的 `Microsoft.Rtc.Internal.Chat.Server.Compliance` 。</span><span class="sxs-lookup"><span data-stu-id="4e22b-109">The interface is defined in the Compliance.dll assembly in the namespace `Microsoft.Rtc.Internal.Chat.Server.Compliance`.</span></span> <span data-ttu-id="4e22b-110">此介面定義了您自訂介面卡必須實作的兩種方法。</span><span class="sxs-lookup"><span data-stu-id="4e22b-110">The interface defines two methods that your custom adapter must implement.</span></span>

    void SetConfig(AdapterConfig config)

<span data-ttu-id="4e22b-111">當配接器第一次載入時，Persistent Chat 規範伺服器會呼叫此方法。</span><span class="sxs-lookup"><span data-stu-id="4e22b-111">The Persistent Chat Compliance server will call this method when the adapter first loads.</span></span> <span data-ttu-id="4e22b-112">`AdapterConfig`包含與規範介面卡相關的 Persistent Chat 相容性設定。</span><span class="sxs-lookup"><span data-stu-id="4e22b-112">The `AdapterConfig` contains the Persistent Chat compliance configuration that is relevant to the compliance adapter.</span></span>

    void Translate(ConversationCollection conversations)

<span data-ttu-id="4e22b-113">只要有要翻譯的新資料，Persistent Chat 規範伺服器便會定期呼叫此方法。</span><span class="sxs-lookup"><span data-stu-id="4e22b-113">The Persistent Chat Compliance server calls this method at periodic intervals as long as there is new data to translate.</span></span> <span data-ttu-id="4e22b-114">此時間間隔相當於 `RunInterval` 持續性聊天規範設定中的設定。</span><span class="sxs-lookup"><span data-stu-id="4e22b-114">This time interval is equal to the `RunInterval` as set in the Persistent Chat Compliance configuration.</span></span>

<span data-ttu-id="4e22b-115">`ConversationCollection`包含上次呼叫此方法時所收集到的交談資訊。</span><span class="sxs-lookup"><span data-stu-id="4e22b-115">The `ConversationCollection` contains the conversation information that was collected from the last time this method was called.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

