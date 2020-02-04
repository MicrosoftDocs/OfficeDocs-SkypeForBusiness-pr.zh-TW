---
title: Lync Server 2013：以自訂的永久性聊天伺服器合規性配接器取代 XmlAdapter
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
ms.openlocfilehash: 9235c57a055131049251d17b75f73a4370cc5f2c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746683"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="replacing-the-xmladapter-with-a-customized-persistent-chat-server-compliance-adapter-in-lync-server-2013"></a><span data-ttu-id="cc4a4-102">在 Lync Server 2013 中使用自訂的持續聊天伺服器合規性配接器來取代 XmlAdapter</span><span class="sxs-lookup"><span data-stu-id="cc4a4-102">Replacing the XmlAdapter with a customized Persistent Chat Server Compliance adapter in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cc4a4-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="cc4a4-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="cc4a4-104">您可以撰寫自訂配接器，而不是使用隨持續聊天伺服器一起安裝的 XmlAdapter。</span><span class="sxs-lookup"><span data-stu-id="cc4a4-104">You can write a custom adapter instead of using the XmlAdapter that is installed with Persistent Chat Server.</span></span> <span data-ttu-id="cc4a4-105">若要完成這項作業，您必須提供包含實現**IComplianceAdapter**介面之公用類別的 .net Framework 元件。</span><span class="sxs-lookup"><span data-stu-id="cc4a4-105">To accomplish this, you must provide a .NET Framework assembly that contains a public class that implements the **IComplianceAdapter** interface.</span></span> <span data-ttu-id="cc4a4-106">您必須將此元件放在持續聊天伺服器池中每個伺服器的 [永久聊天伺服器安裝] 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="cc4a4-106">You must place this assembly in the Persistent Chat Server installation folder of each server in your Persistent Chat Server pool.</span></span> <span data-ttu-id="cc4a4-107">任何一個合規性伺服器都可以為您的配接器提供合規性資料，但合規性伺服器將不會提供重複的合規性資料給您的配接器的多個實例。</span><span class="sxs-lookup"><span data-stu-id="cc4a4-107">Any one of the Compliance servers can provide compliance data to your adapter, but the compliance servers will not provide duplicate compliance data to multiple instances of your adapter.</span></span>

<div>

## <a name="implementing-the-icomplianceadapter-interface"></a><span data-ttu-id="cc4a4-108">實現 IComplianceAdapter 介面</span><span class="sxs-lookup"><span data-stu-id="cc4a4-108">Implementing the IComplianceAdapter interface</span></span>

<span data-ttu-id="cc4a4-109">介面是在命名空間`Microsoft.Rtc.Internal.Chat.Server.Compliance`的合規性 .dll 程式集中定義。</span><span class="sxs-lookup"><span data-stu-id="cc4a4-109">The interface is defined in the Compliance.dll assembly in the namespace `Microsoft.Rtc.Internal.Chat.Server.Compliance`.</span></span> <span data-ttu-id="cc4a4-110">介面定義您的自訂配接器必須實現的兩種方法。</span><span class="sxs-lookup"><span data-stu-id="cc4a4-110">The interface defines two methods that your custom adapter must implement.</span></span>

    void SetConfig(AdapterConfig config)

<span data-ttu-id="cc4a4-111">在配接器第一次載入時會呼叫此方法。</span><span class="sxs-lookup"><span data-stu-id="cc4a4-111">The Persistent Chat Compliance server will call this method when the adapter first loads.</span></span> <span data-ttu-id="cc4a4-112">`AdapterConfig`包含與合規性配接器相關的持續聊天相容性設定。</span><span class="sxs-lookup"><span data-stu-id="cc4a4-112">The `AdapterConfig` contains the Persistent Chat compliance configuration that is relevant to the compliance adapter.</span></span>

    void Translate(ConversationCollection conversations)

<span data-ttu-id="cc4a4-113">只要有要翻譯的新資料，持續性聊天規範伺服器就會以週期性的間隔呼叫此方法。</span><span class="sxs-lookup"><span data-stu-id="cc4a4-113">The Persistent Chat Compliance server calls this method at periodic intervals as long as there is new data to translate.</span></span> <span data-ttu-id="cc4a4-114">此時間間隔等於在持續聊天`RunInterval`相容性設定中設定的。</span><span class="sxs-lookup"><span data-stu-id="cc4a4-114">This time interval is equal to the `RunInterval` as set in the Persistent Chat Compliance configuration.</span></span>

<span data-ttu-id="cc4a4-115">`ConversationCollection`包含上次呼叫此方法時所收集的交談資訊。</span><span class="sxs-lookup"><span data-stu-id="cc4a4-115">The `ConversationCollection` contains the conversation information that was collected from the last time this method was called.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

