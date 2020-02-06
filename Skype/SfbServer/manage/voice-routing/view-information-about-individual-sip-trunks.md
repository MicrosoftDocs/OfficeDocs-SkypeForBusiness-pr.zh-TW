---
title: 在商務用 Skype Server 中查看個別 SIP trunks 的相關資訊
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 在商務用 Skype Server 中，可以將多個 trunks 指派給單一 PSTN 閘道;這表示閘道與 trunks 不是一個，且系統管理員必須使用 CsTrunk Cmdlet 來查看個別 SIP 幹線的相關資訊。
ms.openlocfilehash: d7db7eebfc409b0f79bd562606368d434ba47f0c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816922"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a><span data-ttu-id="5934b-103">在商務用 Skype Server 中查看個別 SIP trunks 的相關資訊</span><span class="sxs-lookup"><span data-stu-id="5934b-103">View information about individual SIP trunks in Skype for Business Server</span></span>

<span data-ttu-id="5934b-104">在商務用 Skype Server 中，可以將多個 trunks 指派給單一 PSTN 閘道;這表示閘道與 trunks 不是一個且相同，且系統管理員必須使用[CsTrunk](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunk) Cmdlet 來查看個別 SIP 幹線的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="5934b-104">In Skype for Business Server, multiple trunks can be assigned to a single PSTN gateway; this means that gateways and trunks are not one and the same, and that administrators must use the [Get-CsTrunk](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunk) cmdlet to view information about an individual SIP trunk.</span></span>

<span data-ttu-id="5934b-105">CsTrunk Cmdlet 可以從商務用 Skype Server Management 命令介面或從 Windows PowerShell 遠端會話執行。</span><span class="sxs-lookup"><span data-stu-id="5934b-105">The Get-CsTrunk cmdlet can be run either from the  Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span>

<span data-ttu-id="5934b-106">**若要查看所有 SIP trunks 的相關資訊**</span><span class="sxs-lookup"><span data-stu-id="5934b-106">**To view information for all your SIP trunks**</span></span>

<span data-ttu-id="5934b-107">下列命令會傳回貴組織中使用的所有 SIP trunks 資訊：</span><span class="sxs-lookup"><span data-stu-id="5934b-107">The following command returns information about all the SIP trunks in use in your organization:</span></span>

`Get-CsTrunk`

<span data-ttu-id="5934b-108">**若要查看特定 SIP 主幹的資訊**</span><span class="sxs-lookup"><span data-stu-id="5934b-108">**To view information for a specific SIP trunk**</span></span>

<span data-ttu-id="5934b-109">這個命令只會傳回具有身分識別 PstnGateway 的 SIP 幹線資訊：192.168.0.240：</span><span class="sxs-lookup"><span data-stu-id="5934b-109">This command returns information only for the SIP trunk with the Identity PstnGateway:192.168.0.240:</span></span>

`Get-CsTrunk -Identity "PstnGateway:192.168.0.240"`

<span data-ttu-id="5934b-110">**查看指派給某個池之所有 SIP Trunks 的相關資訊**</span><span class="sxs-lookup"><span data-stu-id="5934b-110">**Viewing Information for All the SIP Trunks Assigned to a Pool**</span></span>

<span data-ttu-id="5934b-111">在這個範例中，會針對指派給 pool atl-cs-001.litwareinc.com 的所有 SIP trunks 傳回信息：</span><span class="sxs-lookup"><span data-stu-id="5934b-111">In this example, information is returned for all the SIP trunks assigned to the pool atl-cs-001.litwareinc.com:</span></span>

`Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"`
