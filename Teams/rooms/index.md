---
title: Microsoft Teams 會議室
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
feedback_system: None
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b4e0ad1e-12e5-4130-aec1-d8c9cd3a5965
description: 部署 Microsoft 團隊聊天室的相關規劃考慮，以及如何部署及管理系統。
ms.openlocfilehash: 2cba74f72016b51446f7721041039faedd865866
ms.sourcegitcommit: 18838ed1da69ab4668c903bfcafd4ad2fa02639d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/17/2020
ms.locfileid: "44773378"
---
# <a name="microsoft-teams-rooms"></a><span data-ttu-id="0ab85-103">Microsoft Teams 會議室</span><span class="sxs-lookup"><span data-stu-id="0ab85-103">Microsoft Teams Rooms</span></span>

<span data-ttu-id="0ab85-104">將小型 huddle 區域的會議空間轉換成大型的會議室，利用豐富且共同作業的小組體驗，輕鬆使用、部署及管理。</span><span class="sxs-lookup"><span data-stu-id="0ab85-104">Transform meeting spaces ranging from small huddle areas to large conference rooms with a rich, collaborative Teams experience that's simple to use, deploy, and manage.</span></span>

<span data-ttu-id="0ab85-105">透過單一觸控式加入來開啟會議，然後立即將專案投影到聊天室中的顯示，並與遠端參與者共用。</span><span class="sxs-lookup"><span data-stu-id="0ab85-105">Start meetings on time with one-touch join, then instantly project to the display in the room and share to remote participants.</span></span>

<span data-ttu-id="0ab85-106">從其中一個合作夥伴選取正確的系統和音訊視頻外設： Yealink、Logitech、Crestron、Polycom、聯想和 HP。</span><span class="sxs-lookup"><span data-stu-id="0ab85-106">Select the right system and audio video peripherals from one of our partners: Yealink, Logitech, Crestron, Polycom, Lenovo, and HP.</span></span>

:::image type="content" source="../media/srs-room.jpg" alt-text="含 Microsoft 團隊聊天室裝置的會議資料表":::

|               |               |               |               |               |               |
| ------------- | ------------- | ------------- | ------------- | ------------- | ------------- |
| ![清單符號](https://docs.microsoft.com/office/media/icons/list-123-teams.svg)  | <span data-ttu-id="0ab85-109">**[規劃](https://docs.microsoft.com/MicrosoftTeams/rooms/rooms-plan)**</span><span class="sxs-lookup"><span data-stu-id="0ab85-109">**[Plan](https://docs.microsoft.com/MicrosoftTeams/rooms/rooms-plan)**</span></span>  | ![部署符號](https://docs.microsoft.com/office/media/icons/deploy-teams.svg)  | <span data-ttu-id="0ab85-111">**[部署](https://docs.microsoft.com/MicrosoftTeams/rooms/rooms-deploy)**</span><span class="sxs-lookup"><span data-stu-id="0ab85-111">**[Deploy](https://docs.microsoft.com/MicrosoftTeams/rooms/rooms-deploy)**</span></span>  | ![工具/扳手](https://docs.microsoft.com/office/media/icons/toolbox.svg)  | <span data-ttu-id="0ab85-113">**[管理](https://docs.microsoft.com/MicrosoftTeams/rooms/rooms-manage)**</span><span class="sxs-lookup"><span data-stu-id="0ab85-113">**[Manage](https://docs.microsoft.com/MicrosoftTeams/rooms/rooms-manage)**</span></span> |

<br>

> [!NOTE]
> <span data-ttu-id="0ab85-114">Microsoft [團隊聊天室] 適用于 Microsoft 團隊、商務用 Skype Online、商務用 skype Server 2019，或商務用 Skype Server 2015。</span><span class="sxs-lookup"><span data-stu-id="0ab85-114">Microsoft Teams Rooms is intended for use with Microsoft Teams, Skype for Business Online, Skype for Business Server 2019, or Skype for Business Server 2015.</span></span>  <br><br><span data-ttu-id="0ab85-115">較舊的平臺（例如 Lync Server 2013）不應與 Microsoft 團隊聊天室搭配使用。</span><span class="sxs-lookup"><span data-stu-id="0ab85-115">Earlier platforms like Lync Server 2013 aren't expected to work with Microsoft Teams Rooms.</span></span>

<span data-ttu-id="0ab85-116">這些文章適用于負責規劃、部署及管理這些裝置的人員，不適用於系統使用者。</span><span class="sxs-lookup"><span data-stu-id="0ab85-116">These articles are intended for people tasked with planning, deploying, and managing these devices, and not for the users of the system.</span></span> <span data-ttu-id="0ab85-117">使用者將對 Microsoft 團隊聊天室[線上](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)說明更感興趣。</span><span class="sxs-lookup"><span data-stu-id="0ab85-117">Users will be more interested in the Microsoft Teams Rooms [online help](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).</span></span>

> [!NOTE]
> <span data-ttu-id="0ab85-118">[Skype 室系統](../rooms/lrs-migration.md)（舊稱 Lync 房間系統）和 Microsoft 團隊聊天室是不同的產品，具有不同的相依性與部署程式。</span><span class="sxs-lookup"><span data-stu-id="0ab85-118">[Skype Room System](../rooms/lrs-migration.md) (formerly Lync Room System) and Microsoft Teams Rooms are different products with different dependencies and deployment procedures.</span></span>
