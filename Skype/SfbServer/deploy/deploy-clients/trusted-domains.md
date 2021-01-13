---
title: Skype 室系統信任的網域
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
description: 閱讀此主題以瞭解如何為 Skype 會議室系統和商務用 Skype 設定信任的網域。
ms.openlocfilehash: c7883ed0cbc2e805ee0ba3cddfb3b2cee1163c35
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834113"
---
# <a name="skype-room-system-trusted-domains"></a>Skype 室系統信任的網域
 
閱讀此主題以瞭解如何為 Skype 會議室系統和商務用 Skype 設定信任的網域。
  
## <a name="trusted-domains"></a>信任的網域

商務用 Skype 用戶端會顯示一個對話方塊，可讓使用者在登入的使用者帳戶的 SIP 網域與憑證上的主語或主體替代名稱中所呈現的名稱不同時，接受來自商務用 Skype 伺服器的憑證。 如果為組織中的商務用 Skype 伺服器設定的憑證沒有以主旨或主體替代名稱顯示的 Skype 會議室系統帳戶的 SIP 功能變數名稱，您必須在商務用 Skype 系統主控台機器上，設定 [信任的網域] 登錄機碼底下的憑證所呈現的網域。 您的 Skype 會議室系統製造商-提供的 skype 會議室系統管理員指南說明如何在商務用 Skype 用戶端中新增信任的網域。 
  
例如，假設在商務用 Skype Server 上設定的憑證具有「CONTOSO」的主體/主體替代名稱。LOCAL "和指派給使用者之 Skype 會議室系統登入位址的其中一個 SIP 網域為" confrm1@contoso.net "。 由於 contoso.net 不在憑證中，在 Skype 聊天室系統電腦上，您必須將 "contoso" 設定為登錄中的信任網域，如您的 Skype 會議室系統製造商提供的 skype 會議室系統管理員指南所述。 
  

