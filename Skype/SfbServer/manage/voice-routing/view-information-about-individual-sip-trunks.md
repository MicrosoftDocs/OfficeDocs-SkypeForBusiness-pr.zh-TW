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
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a>在商務用 Skype Server 中查看個別 SIP 主幹的相關資訊

在商務用 Skype Server 中，可將多個主幹指派給單一 PSTN 閘道;這表示閘道和主幹不是一個，而且必須使用 [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk) Cmdlet 來查看個別 SIP 主幹的相關資訊。

Get-CsTrunk Cmdlet 可以從商務用 Skype Server 管理命令介面或從 Windows PowerShell 的遠端會話執行。

**若要查看所有 SIP 主幹的資訊**

下列命令會傳回組織中使用之所有 SIP 主幹的資訊：

`Get-CsTrunk`

**若要查看特定 SIP 主幹的資訊**

這個命令只會傳回身分識別 PstnGateway:192.168.0.240 的 SIP 主幹資訊：

`Get-CsTrunk -Identity "PstnGateway:192.168.0.240"`

**查看指派至集區之所有 SIP 主幹的資訊**

在此範例中，會傳回指派給集區 atl-cs-001.litwareinc.com 的所有 SIP 主幹的資訊：

`Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"`
