---
title: Skype會議室系統信任的網域
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9fb63ad4-6eda-4724-be63-10bf5e65cb2b
description: 閱讀此主題以瞭解如何設定 Skype 會議室系統和商務用 Skype 的信任網域。
ms.openlocfilehash: 0cdf7806a40dbbe440614e7d9407926cb17a6a2e817a73c6c0026b0d7078ee19
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54298723"
---
# <a name="skype-room-system-trusted-domains"></a>Skype會議室系統信任的網域
 
閱讀此主題以瞭解如何設定 Skype 會議室系統和商務用 Skype 的信任網域。
  
## <a name="trusted-domains"></a>信任的網域

商務用 Skype 用戶端會顯示一個對話方塊，讓使用者在登入的使用者帳戶的 SIP 網域與憑證上的主語或主體替代名稱中所呈現的名稱不同的情況時，接受來自商務用 Skype Server 的憑證。 如果為組織中的商務用 Skype Server 所設定的憑證沒有以主旨或主體替代名稱 Skype 會議室系統帳戶的 SIP 功能變數名稱，您必須在 [Skype 機房系統] 主控台機器上，設定 [信任的網域] 登錄機碼底下的憑證所呈現的網域。 您的 Skype 會議室系統製造商-提供 Skype 會議室系統管理員指南說明如何在商務用 Skype 用戶端中新增信任的網域。 
  
例如，假設商務用 Skype Server 上所設定的憑證具有「CONTOSO」的主體/主體替代名稱。LOCAL "和指派給使用者 Skype 聊天室系統登入位址的其中一個 SIP 網域為" confrm1@contoso.net "。 因為 contoso.net 不在憑證中，所以在 Skype 的聊天室系統電腦上，您必須將 "contoso" 設定為登錄中的信任網域，如您 Skype 會議室系統製造商中所述，如您所述 Skype 的會議室系統管理員指南所述。 
  

