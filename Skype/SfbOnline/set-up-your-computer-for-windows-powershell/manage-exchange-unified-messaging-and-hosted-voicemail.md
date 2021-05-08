---
title: 管理 Exchange 整合通訊與託管語音信箱
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 707198df-df85-4833-9c15-aa29b71f085c
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
description: 使用 PowerShell 在 Exchange管理統一訊息功能，例如自動語音信箱和訂閱者存取，以及 商務用 Skype語音信箱。
ms.openlocfilehash: 1a841b377fbc84d85f085dc9d479fa05cc0b2be4
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238736"
---
# <a name="manage-exchange-unified-messaging-and-hosted-voicemail"></a>管理 Exchange 整合通訊與託管語音信箱

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

您可以使用一Exchange Cmdlet 在 商務用 Skype Online 中管理統一訊息和主商務用 Skype語音信箱。
  
## <a name="manage-exchange-unified-messaging-and-hosted-voice-mail"></a>管理Exchange郵件和託管語音信箱

下列 Cmdlet 可用來管理 UM Exchange和託管語音信箱 (統一) 訊息：
  

| **Cmdlet**                                                                                                                                                                                                                                                                                                                        | **描述**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [Get-CsExUmContact](/powershell/module/skype/Get-CsExUmContact) <br/><br/> [New-CsExUmContact](/powershell/module/skype/New-CsExUmContact) <br/> <br/>[Remove-CsExUmContact](/powershell/module/skype/Remove-CsExUmContact) <br/> <br/>[Set-CsExUmContact](/powershell/module/skype/Set-CsExUmContact) <br/> | 建立及管理用於自動總機和訂閱者 Access 服務的連絡人物件，Exchange UM 是託管服務時。  <br/><br/> 商務用 SkypeOnline 可Exchange UM，提供數種語音相關功能，包括自動語音助理和訂閱者存取。 自動回應提供自動接聽電話的方式，並路由給正確的人員。 訂閱者 Access 可讓使用者Exchange UM，並取得電子郵件、語音留言、連絡人和日曆資訊。  <br/><br/> 當 Exchange UM 作為託管服務提供時，用於自動助理和訂閱者 Access 服務的連絡人物件必須使用 Microsoft PowerShell 建立。 這些物件是使用 **CsExUmContact** Cmdlet 建立和管理。 <br/> |
| [Get-CSHostedVoicemailPolicy](/powershell/module/skype/Grant-CsHostedVoicemailPolicy) <br/> <br/>[Grant-CSHostedVoicemailPolicy](/powershell/module/skype/Set-CsTenantPublicProvider) <br/>                                                                                                                                                | 管理組織中所使用的託管語音信箱政策。 託管語音信箱政策會指定未接聽的來電如何路由至Exchange UM 服務。 這些策略只會影響已啟用 UM Exchange語音信箱的使用者。  <br/><br/> 若要驗證使用者是否已啟用託管語音信箱，請從 PowerShell 提示執行類似下列的命令。  <br/> \`Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"                                                                                                                                                                                                                                                                                                                                                           |

## <a name="related-topics"></a>相關主題
[使用電腦設定商務用 skype 線上管理Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
