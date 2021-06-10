---
title: 設定混合式Exchange組織
author: dstrome
ms.author: dstrome
manager: serdars
ms.date: 09/25/2017
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: dstrome
description: 瞭解如何設定一個Exchange混合式組織，Microsoft Teams群組成員資格同步處理。
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 90250b3d3f3593990d356843bebea324060d6f8b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094605"
---
<a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a><span data-ttu-id="f0802-103">設定一Exchange混合式組織，以用於Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f0802-103">Configure an Exchange hybrid organization for use with Microsoft Teams</span></span>
======================================================================

<span data-ttu-id="f0802-104">一般而言，您不應設定任何Exchange Online功能，以用於Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="f0802-104">Generally, you should not have to configure any Exchange Online functionality for use with Microsoft Teams.</span></span> <span data-ttu-id="f0802-105">不過，Exchange混合式案例時，需要採取一些步驟，以確保群組成員資格在 Exchange Server (內部部署和) 之間Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="f0802-105">However, for Exchange Hybrid scenarios, there are steps necessary to ensure Group memberships are synchronized between Exchange Server (on-premises) and Exchange Online.</span></span> <span data-ttu-id="f0802-106">這涉及啟用 Azure AD 連線的群組寫回功能，以及各種初始化腳本：使用內部部署Microsoft 365[混合](/exchange/hybrid-deployment/set-up-microsoft-365-groups)式設定 Exchange群組。</span><span class="sxs-lookup"><span data-stu-id="f0802-106">This involves enablement of Group Writeback functionality in Azure AD Connect along with various initialization scripts: [Configure Microsoft 365 Groups with on-premises Exchange hybrid](/exchange/hybrid-deployment/set-up-microsoft-365-groups).</span></span>