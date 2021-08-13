---
title: 在 Lync 2010 用戶端電腦上設定個人連絡人存放區
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.openlocfilehash: 806bdf8ac43c8126e0537ccb121cbc521066aab6cd42c7136d0d8b951d5b9d19
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54319456"
---
# <a name="configure-the-personal-contacts-store-on-lync-2010-client-computers"></a>在 Lync 2010 用戶端電腦上設定個人連絡人存放區
  
如果您要將商務用 Skype Server 2015 和 Exchange Server 2016 或 Exchange Server 2013 整合在一起，則應該設定用戶端所使用的個人連絡人存放區。 尤其是，您應該設定商務用 Skype 以使用 Exchange 做為個人連絡人存放區，並同時確定使用者無法覆寫該決策。 您可以在每一部用戶端電腦上建立及設定登錄值，以完成此動作。
  
> [!NOTE]
> 下列程式只需要使用 Lync 2010 用戶端或更早版本的用戶端。 Lync 2013 用戶端和所有商務用 Skype 用戶端將不會有覆寫連絡人存放區設定的選項。
  
若要在單一電腦上設定此值，請完成下列程式：
  
1. 在用戶端電腦上，按一下 [ **開始** ]，然後按一下 [ **執行**]。
2. 在 [執行] 對話方塊中，輸入 regedit，然後按 ENTER。
3. 在 [登錄編輯程式] 中，展開 [ **HKEY_LOCAL_MACHINE**]、[**軟體**]、[**原則**]、[ **Microsoft**]，然後展開 **Communicator**。
4. 以滑鼠右鍵按一下 [ **Communicator**]，指向 [**新增**]，然後按一下 [ **DWORD (32-位) 值**。
5. 建立新值後，輸入 PersonalContactStoreOverride，然後按 ENTER 鍵來重新命名值。
6. 確認 PersonalContactStoreOverride 的值設為0，然後關閉 [登錄編輯程式]。

如果您需要在多部電腦上進行相同的變更，您可以建立自訂的群組原則物件。 如需在 Windows 10 中執行此動作的詳細資訊，請參閱[建立群組原則物件一](/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)文。
