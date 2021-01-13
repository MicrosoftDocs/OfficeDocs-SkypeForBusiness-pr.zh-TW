---
title: 在商務用 Skype Server 中查看個別 SIP 主幹的相關資訊
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 在商務用 Skype Server 中，可將多個主幹指派給單一 PSTN 閘道;這表示閘道和主幹不是一或相同，管理員必須使用 Get-CsTrunk Cmdlet 來查看個別 SIP 主幹的相關資訊。
ms.openlocfilehash: b49846ed7244dec2f51f51f262becc440662026c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826173"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a><span data-ttu-id="af0d4-103">在商務用 Skype Server 中查看個別 SIP 主幹的相關資訊</span><span class="sxs-lookup"><span data-stu-id="af0d4-103">View information about individual SIP trunks in Skype for Business Server</span></span>

<span data-ttu-id="af0d4-104">在商務用 Skype Server 中，可將多個主幹指派給單一 PSTN 閘道;這表示閘道和主幹不是一個，而且必須使用 [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk) Cmdlet 來查看個別 SIP 主幹的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="af0d4-104">In Skype for Business Server, multiple trunks can be assigned to a single PSTN gateway; this means that gateways and trunks are not one and the same, and that administrators must use the [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk) cmdlet to view information about an individual SIP trunk.</span></span>

<span data-ttu-id="af0d4-105">Get-CsTrunk Cmdlet 可以從商務用 Skype Server 管理命令介面或從 Windows PowerShell 的遠端會話執行。</span><span class="sxs-lookup"><span data-stu-id="af0d4-105">The Get-CsTrunk cmdlet can be run either from the  Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span>

<span data-ttu-id="af0d4-106">**若要查看所有 SIP 主幹的資訊**</span><span class="sxs-lookup"><span data-stu-id="af0d4-106">**To view information for all your SIP trunks**</span></span>

<span data-ttu-id="af0d4-107">下列命令會傳回組織中使用之所有 SIP 主幹的資訊：</span><span class="sxs-lookup"><span data-stu-id="af0d4-107">The following command returns information about all the SIP trunks in use in your organization:</span></span>

`Get-CsTrunk`

<span data-ttu-id="af0d4-108">**若要查看特定 SIP 主幹的資訊**</span><span class="sxs-lookup"><span data-stu-id="af0d4-108">**To view information for a specific SIP trunk**</span></span>

<span data-ttu-id="af0d4-109">這個命令只會傳回身分識別 PstnGateway:192.168.0.240 的 SIP 主幹資訊：</span><span class="sxs-lookup"><span data-stu-id="af0d4-109">This command returns information only for the SIP trunk with the Identity PstnGateway:192.168.0.240:</span></span>

`Get-CsTrunk -Identity "PstnGateway:192.168.0.240"`

<span data-ttu-id="af0d4-110">**查看指派至集區之所有 SIP 主幹的資訊**</span><span class="sxs-lookup"><span data-stu-id="af0d4-110">**Viewing Information for All the SIP Trunks Assigned to a Pool**</span></span>

<span data-ttu-id="af0d4-111">在此範例中，會傳回指派給集區 atl-cs-001.litwareinc.com 的所有 SIP 主幹的資訊：</span><span class="sxs-lookup"><span data-stu-id="af0d4-111">In this example, information is returned for all the SIP trunks assigned to the pool atl-cs-001.litwareinc.com:</span></span>

`Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"`
