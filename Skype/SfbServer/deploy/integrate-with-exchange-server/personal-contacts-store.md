---
title: 在 Lync 2010 用戶端電腦上設定個人連絡人存放區
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 1/29/2019
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
description: 摘要：設定舊版用戶端所使用的個人連絡人存放區。
ms.openlocfilehash: a80af6ca575b53e5a2b8f77a109fd6929f0db704
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41797024"
---
# <a name="configure-the-personal-contacts-store-on-lync-2010-client-computers"></a>在 Lync 2010 用戶端電腦上設定個人連絡人存放區
  
如果您整合的是商務用 Skype Server 2015 與 Exchange Server 2016 或 Exchange Server 2013，那麼您應該設定用戶端所使用的個人連絡人存放區。 特別是，您應該將商務用 Skype 設定為使用 Exchange 作為個人連絡人存放區，並同時確定使用者無法覆寫該決策。 您可以在每個用戶端電腦上建立並設定登錄值來完成這項工作。
  
> [!NOTE]
> 下列程式僅適用于使用 Lync 2010 用戶端或較舊版本的用戶端。 Lync 2013 用戶端及所有商務用 Skype 用戶端將無法選擇覆寫連絡人存放區設定。
  
若要在單一電腦上設定此值，請完成下列程式：
  
1. 在用戶端電腦上，按一下 [**開始**]，然後按一下 [**執行**]。
2. 在 [**執行**] 對話方塊中，輸入 regedit，然後按 enter。
3. 在 [登錄編輯程式] 中，展開 [ **HKEY_LOCAL_MACHINE**]，展開 [**軟體**]，然後展開 [**原則**]、[ **Microsoft**]，然後展開 [ **Communicator**
4. 以滑鼠右鍵按一下 [ **Communicator**]，指向 [**新增**]，然後按一下 **[DWORD （32位）] 值**。
5. 建立新值之後，請輸入 PersonalContactStoreOverride，然後按 ENTER 鍵來重新命名值。
6. 確認 PersonalContactStoreOverride 的值設定為0，然後關閉 [登錄編輯程式]。

如果您需要在多部電腦上進行相同的變更，您可以建立自訂的群組原則物件來執行此動作。 如需在 Windows 10 中執行此動作的詳細資訊，請參閱[建立群組原則物件](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)一文。
  
