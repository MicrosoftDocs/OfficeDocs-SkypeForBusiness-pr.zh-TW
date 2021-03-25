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
description: 使用 PowerShell 在商務用 Skype Online 中管理 Exchange 統一訊息功能，例如自動語音信箱和訂閱者存取，以及託管的語音信箱。
ms.openlocfilehash: 393b0a43cb55462006ef7701396a3b7840032fb4
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113199"
---
# <a name="manage-exchange-unified-messaging-and-hosted-voicemail"></a>管理 Exchange 整合通訊與託管語音信箱

您可以使用一組 Cmdlet 在商務用 Skype Online 中管理 Exchange Unified Messaging 和託管語音信箱。
  
## <a name="manage-exchange-unified-messaging-and-hosted-voice-mail"></a>管理 Exchange 統一訊息和託管語音信箱

下列 Cmdlet 可用於管理 Exchange Unified Messag (UM) 語音信箱策略：
  

| **Cmdlet**                                                                                                                                                                                                                                                                                                                        | **描述**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [Get-CsExUmContact](/powershell/module/skype/Get-CsExUmContact) <br/><br/> [New-CsExUmContact](/powershell/module/skype/New-CsExUmContact) <br/> <br/>[Remove-CsExUmContact](/powershell/module/skype/Remove-CsExUmContact) <br/> <br/>[Set-CsExUmContact](/powershell/module/skype/Set-CsExUmContact) <br/> | 當 Exchange UM 是託管服務時，建立及管理用於自動總機和訂閱者 Access 服務的連絡人物件。  <br/><br/> 商務用 Skype Online 可與 Exchange UM 合作，提供數種語音相關功能，包括自動語音留言和訂閱者存取。 自動回應提供自動接聽電話的方式，並路由給正確的人員。 訂閱者 Access 可讓使用者連接到 Exchange UM，並取得電子郵件、語音留言、連絡人和日曆資訊。  <br/><br/> 當 Exchange UM 是作為託管服務提供時，必須使用 Microsoft PowerShell 建立用於自動總機和訂閱者 Access 服務的連絡人物件。 這些物件是使用 **CsExUmContact** Cmdlet 建立和管理。 <br/> |
| [Get-CSHostedVoicemailPolicy](/powershell/module/skype/Grant-CsHostedVoicemailPolicy) <br/> <br/>[Grant-CSHostedVoicemailPolicy](/powershell/module/skype/Set-CsTenantPublicProvider) <br/>                                                                                                                                                | 管理組織中所使用的託管語音信箱政策。 託管語音信箱政策會指定未接聽的通話如何路由至 Exchange UM 服務。 這些策略只會影響已啟用 Exchange UM 託管語音信箱的使用者。  <br/><br/> 若要驗證使用者是否已啟用託管語音信箱，請從 PowerShell 提示執行類似下列的命令。  <br/> \`Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"                                                                                                                                                                                                                                                                                                                                                           |

## <a name="related-topics"></a>相關主題
[使用 Windows PowerShell 設定商務用 Skype 線上管理的電腦](set-up-your-computer-for-windows-powershell.md)

  
