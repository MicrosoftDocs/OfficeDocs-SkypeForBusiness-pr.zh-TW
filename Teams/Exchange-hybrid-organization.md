---
title: 設定 Exchange 混合式組織
author: dstrome
ms.author: dstrome
manager: serdars
ms.date: 09/25/2017
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: dstrome
description: 瞭解如何設定與 Microsoft 團隊搭配使用的 Exchange 混合式組織。
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 23773ac842b93067dbf3204d81e2a3ad1708a3af
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/22/2020
ms.locfileid: "43778689"
---
<a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a><span data-ttu-id="f75d4-103">設定 Exchange 混合式組織以搭配 Microsoft 團隊使用</span><span class="sxs-lookup"><span data-stu-id="f75d4-103">Configure an Exchange hybrid organization for use with Microsoft Teams</span></span>
======================================================================

<span data-ttu-id="f75d4-104">一般來說，您不需要設定任何 Exchange Online 功能即可與 Microsoft 團隊搭配使用。</span><span class="sxs-lookup"><span data-stu-id="f75d4-104">Generally, you should not have to configure any Exchange Online functionality for use with Microsoft Teams.</span></span> <span data-ttu-id="f75d4-105">不過，針對 Exchange 混合式案例，必須採取一些步驟，才能確保在 Exchange 伺服器（內部部署）與 Exchange Online 之間同步處理群組成員資格。</span><span class="sxs-lookup"><span data-stu-id="f75d4-105">However, for Exchange Hybrid scenarios, there are steps necessary to ensure Group memberships are synchronized between Exchange Server (on-premises) and Exchange Online.</span></span> <span data-ttu-id="f75d4-106">這涉及在 Azure AD Connect 中啟用群組寫回功能，以及各種初始化腳本：[將 Microsoft 365 群組與內部部署 Exchange 混合](https://go.microsoft.com/fwlink/?linkid=854389)式搭配使用。</span><span class="sxs-lookup"><span data-stu-id="f75d4-106">This involves enablement of Group Writeback functionality in Azure AD Connect along with various initialization scripts: [Configure Microsoft 365 Groups with on-premises Exchange hybrid](https://go.microsoft.com/fwlink/?linkid=854389).</span></span>
