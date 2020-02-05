---
title: Skype 室系統信任的網域
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9fb63ad4-6eda-4724-be63-10bf5e65cb2b
description: 請閱讀本主題，瞭解如何針對 Skype 會議室系統和商務用 Skype 設定受信任的網域。
ms.openlocfilehash: 618ea5ce6cd4e12cd1e6a811a065f7a29a5c9ced
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768666"
---
# <a name="skype-room-system-trusted-domains"></a>Skype 室系統信任的網域
 
請閱讀本主題，瞭解如何針對 Skype 會議室系統和商務用 Skype 設定受信任的網域。
  
## <a name="trusted-domains"></a>受信任的網域

商務用 Skype 用戶端會顯示一個對話方塊，讓使用者從商務用 Skype 伺服器接受憑證（如果登入的使用者帳戶的 SIP 網域與憑證上的 Subject 或 Subject 替換名稱中所顯示的名稱不同）。 如果針對貴組織中的商務用 Skype Server 所設定的憑證沒有 Subject 或 Subject 替換名稱中的 Skype 會議室系統帳戶的 SIP 功能變數名稱，您必須設定在信任網域下的憑證上顯示的那些網域。Skype 聊天室系統主控台電腦上的登錄機碼。 您的 Skype 會議室系統製造商-提供的 Skype 會議室系統管理員指南說明如何在商務用 Skype 用戶端中新增受信任網域的方式和位置。 
  
例如，假設在商務用 Skype 伺服器上設定的憑證具有 [CONTOSO] 的主體/Subject 替換名稱。[本機]，而指派給使用者的其中一個 SIP 網域是「confrm1@contoso.net」。 因為 contoso.net 不在憑證中，所以在 Skype 會議室系統電腦上，您需要將「contoso. local」設定為在登錄中受信任的網域，如 Skype 會議室系統製造商提供的 Skype 會議室系統管理員指南中所述。 
  

