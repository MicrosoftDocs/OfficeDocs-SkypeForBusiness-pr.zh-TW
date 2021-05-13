---
title: 應用程式中的應用程式更新Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: v-tbasra
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 瞭解如何更新應用程式中的應用程式Microsoft Teams。
ms.openlocfilehash: b39b831b644b19038b8f4574acf3e5bc5c50d73c
ms.sourcegitcommit: 40f76bc6b5e304faea8516a78f8576ba1cdb7f7c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/12/2021
ms.locfileid: "52337821"
---
# <a name="update-apps-in-microsoft-teams"></a><span data-ttu-id="96db0-103">更新應用程式Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="96db0-103">Update apps in Microsoft Teams</span></span>

<span data-ttu-id="96db0-104">在大多數情況下，應用程式開發人員發佈 App 更新後，新版本會自動顯示給使用者。</span><span class="sxs-lookup"><span data-stu-id="96db0-104">In most cases, after app developers publish an app update, the new version automatically appears for users.</span></span> <span data-ttu-id="96db0-105">不過，系統對 Microsoft Teams<a href="/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">清單</a>有一些更新需要使用者接受才能完成：</span><span class="sxs-lookup"><span data-stu-id="96db0-105">However, there are some updates to the <a href="/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">Microsoft Teams manifest</a> that require user acceptance to complete:</span></span>

* <span data-ttu-id="96db0-106">已新增或移除 Bot</span><span class="sxs-lookup"><span data-stu-id="96db0-106">A bot was added or removed</span></span>
* <span data-ttu-id="96db0-107">現有 Bot 的「botId」屬性已變更</span><span class="sxs-lookup"><span data-stu-id="96db0-107">An existing bot's "botId" property changed</span></span>
* <span data-ttu-id="96db0-108">已變更現有 Bot 的 "isNotificationOnly" 屬性</span><span class="sxs-lookup"><span data-stu-id="96db0-108">An existing bot's "isNotificationOnly" property changed</span></span>
* <span data-ttu-id="96db0-109">Bot 的「支援檔」屬性已變更</span><span class="sxs-lookup"><span data-stu-id="96db0-109">The bot's "supportsFiles" property changed</span></span>
* <span data-ttu-id="96db0-110">已新增或移除訊息擴充功能</span><span class="sxs-lookup"><span data-stu-id="96db0-110">A messaging extension was added or removed</span></span>
* <span data-ttu-id="96db0-111">已新增連接器</span><span class="sxs-lookup"><span data-stu-id="96db0-111">A new connector was added</span></span>
* <span data-ttu-id="96db0-112">已新增靜態定位停駐點</span><span class="sxs-lookup"><span data-stu-id="96db0-112">A new static tab was added</span></span>
* <span data-ttu-id="96db0-113">已新增可配置的選項卡</span><span class="sxs-lookup"><span data-stu-id="96db0-113">A new configurable tab was added</span></span>
* <span data-ttu-id="96db0-114">「webApplicationInfo」中的屬性已變更</span><span class="sxs-lookup"><span data-stu-id="96db0-114">Properties inside "webApplicationInfo" changed</span></span>

![提供新版本](media/manage-your-custom-apps-update1.png)

![應用程式的升級選項](media/manage-your-custom-apps-update2.png)

> [!NOTE] 
> <span data-ttu-id="96db0-117">更新程式適用于 Microsoft App、自訂應用程式和協力廠商應用程式的所有應用程式更新。</span><span class="sxs-lookup"><span data-stu-id="96db0-117">The update process applies to all app updates for Microsoft apps, custom apps, and third-party apps.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="96db0-118">相關主題</span><span class="sxs-lookup"><span data-stu-id="96db0-118">Related topics</span></span>

[<span data-ttu-id="96db0-119">管理應用程式</span><span class="sxs-lookup"><span data-stu-id="96db0-119">Manage apps</span></span>](manage-apps.md)