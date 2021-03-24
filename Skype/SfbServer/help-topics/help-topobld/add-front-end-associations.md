---
title: 新增前端關聯
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndAssociationsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 95620425-defd-47fd-a5c0-e4a283d812a5
description: 現在，您可以將伺服器角色與前端集區產生關聯，對需要部署其他伺服器的特定功能啟用支援。 您也可以稍後將伺服器角色與前端集區產生關聯。 可與前端集區相關聯的伺服器角色包括下列各項：
ms.openlocfilehash: 8ff7d11a40f7eccfda78643fd8b3a17146c014d7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103249"
---
# <a name="add-front-end-associations"></a><span data-ttu-id="f0322-105">新增前端關聯</span><span class="sxs-lookup"><span data-stu-id="f0322-105">Add Front End Associations</span></span>

<span data-ttu-id="f0322-106">現在，您可以將伺服器角色與前端集區產生關聯，對需要部署其他伺服器的特定功能啟用支援。</span><span class="sxs-lookup"><span data-stu-id="f0322-106">You can enable support for specific features that require the deployment of other servers by associating the server roles with the Front End pool now.</span></span> <span data-ttu-id="f0322-107">您也可以稍後將伺服器角色與前端集區產生關聯。</span><span class="sxs-lookup"><span data-stu-id="f0322-107">You can also associate server roles with the Front End pool at a later time.</span></span> <span data-ttu-id="f0322-108">可與前端集區相關聯的伺服器角色包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="f0322-108">The server roles that can be associated with a Front End pool include the following:</span></span>

- <span data-ttu-id="f0322-109">A/V Edge Server。</span><span class="sxs-lookup"><span data-stu-id="f0322-109">A/V Edge Server.</span></span> <span data-ttu-id="f0322-110">如需有關執行 A/V Edge Server 的詳細資訊，請參閱規劃檔中的 [規劃會議](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-conferencing) 。</span><span class="sxs-lookup"><span data-stu-id="f0322-110">For details about the implementation of an A/V Edge Server, see [Planning for Conferencing](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-conferencing) in the Planning documentation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f0322-111">如果您現在啟用上述任一功能的支援，您發佈的拓撲設計將會包含實施每個選取功能所需的伺服器元件。</span><span class="sxs-lookup"><span data-stu-id="f0322-111">If you enable support for any of these features now, the topology design that you publish will include the server components that are required to implement each selected feature.</span></span> <span data-ttu-id="f0322-112">若要將拓撲發行成功，但沒有錯誤，您必須將實體電腦加入網域。</span><span class="sxs-lookup"><span data-stu-id="f0322-112">For the publishing of a topology to succeed without error, you must have the physical computers joined to the domain.</span></span> <span data-ttu-id="f0322-113">例如，如果您現在啟用封存支援，則必須先部署封存伺服器並設定適當的封存選項，才能開始封存組織的通訊。</span><span class="sxs-lookup"><span data-stu-id="f0322-113">For example, if you enable support for archiving now, you must then deploy an Archiving Server and configure the appropriate archiving options before you start archiving communications for your organization.</span></span>