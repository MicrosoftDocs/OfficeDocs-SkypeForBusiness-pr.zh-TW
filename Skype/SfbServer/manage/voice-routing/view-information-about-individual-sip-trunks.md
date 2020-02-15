---
title: 檢視 Business server Skype 中的個別 SIP 主幹的相關資訊
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
description: Skype for Business Server，多個主幹可以指派給單一的 PSTN 閘道;這表示閘道和主幹不是同一個，而且系統管理員必須使用 Get-cstrunk cmdlet 來檢視個別 SIP 主幹的資訊。
ms.openlocfilehash: c5288e676f546e07504f4d8609fcea63913b6457
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048176"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a>檢視 Business server Skype 中的個別 SIP 主幹的相關資訊

Skype for Business Server，多個主幹可以指派給單一的 PSTN 閘道;這表示閘道及主幹不是同一個，而系統管理員必須使用[Get-cstrunk](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk) cmdlet 來檢視個別 SIP 主幹的資訊。

可以執行 Get-cstrunk cmdlet，從 Skype for Business Server 管理命令介面或 Windows PowerShell 的遠端工作階段。

**若要檢視所有 SIP 主幹的資訊**

下列命令會傳回用於組織中所有 SIP 主幹的資訊：

`Get-CsTrunk`

**若要檢視特定 SIP 主幹的資訊**

此命令會傳回 192.168.0.240 身分識別的 SIP 主幹的資訊：

`Get-CsTrunk -Identity "PstnGateway:192.168.0.240"`

**檢視指派給集區的所有 SIP 主幹的資訊**

在這個範例中，傳回指派給 atl-cs-001.litwareinc.com 集區的所有 SIP 主幹資訊-atl-cs-001.litwareinc.com:

`Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"`
