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
description: 在商務用 Skype Online 中使用 PowerShell 管理 Exchange 整合通訊功能，例如自動語音應答及訂閱者存取及託管語音信箱。
ms.openlocfilehash: d0c2ff8cad705a2d00685e2c6935616ab8d64ac9
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41692678"
---
# <a name="manage-exchange-unified-messaging-and-hosted-voicemail"></a>管理 Exchange 整合通訊與託管語音信箱

您可以使用一組 Cmdlet，在商務用 Skype Online 中管理 Exchange 整合訊息及託管語音信箱。
  
## <a name="manage-exchange-unified-messaging-and-hosted-voice-mail"></a>管理 Exchange 整合訊息及託管語音信箱

下列 Cmdlet 可用來管理 Exchange 整合通訊（UM）及託管的語音信箱原則：
  

| **Cmdlet**                                                                                                                                                                                                                                                                                                                        | **說明**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849628) <br/><br/> [新-CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849629) <br/> <br/>[移除-CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849630) <br/> <br/>[Set-CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849631) <br/> | 如果 Exchange UM 是託管服務，就會建立並管理用於自動語音應答及訂閱者存取服務的連絡人物件。  <br/><br/> 商務用 Skype Online 可與 Exchange UM 搭配使用，以提供多種語音相關功能，包括自動助理及訂閱者存取。 自動語音應答提供通話自動接聽的方式，並路由至正確的人員。 [訂閱者存取] 可讓使用者連線到 Exchange UM 並檢索電子郵件、語音訊息、連絡人和行事曆資訊。  <br/><br/> 當 Exchange UM 是作為託管服務提供時，必須使用 Microsoft PowerShell 來建立用於自動語音應答和訂閱者存取服務的連絡人物件。 這些物件是使用**CsExUmContact** Cmdlet 來建立和管理。 <br/> |
| [CSHostedVoicemailPolicy](https://go.microsoft.com/fwlink/p/?linkid=849633) <br/> <br/>[授與 CSHostedVoicemailPolicy](https://go.microsoft.com/fwlink/p/?linkid=849602) <br/>                                                                                                                                                | 管理組織中使用的託管語音信箱原則。 託管的語音信箱原則可指定未應答的呼叫路由至 Exchange UM 服務的方式。 這些原則只會影響已針對 Exchange UM 託管語音信箱啟用的使用者。  <br/><br/> 若要確認使用者是否已啟用託管的語音信箱，請從 PowerShell 提示執行類似下列的命令。  <br/> \`CsOnlineUser-身分識別 "kenmyer@litwareinc.com"                                                                                                                                                                                                                                                                                                                                                           |

## <a name="related-topics"></a>相關主題
[使用 Windows PowerShell 設定商務用 skype online 管理電腦](set-up-your-computer-for-windows-powershell.md)

  
 
