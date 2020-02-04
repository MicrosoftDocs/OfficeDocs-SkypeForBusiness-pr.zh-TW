---
title: Lync Server 2013：指派每位使用者託管的語音信箱原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user hosted voice mail policy
ms:assetid: d44c71a0-4407-4ab4-b7e0-d671dde3425f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398919(v=OCS.15)
ms:contentKeyID: 48185456
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 95413733a9b23ce1f749ebb16521a3349b00165d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722953"
---
# <a name="assign-a-per-user-hosted-voice-mail-policy-in-lync-server-2013"></a>在 Lync Server 2013 中指派每個使用者託管的語音信箱原則

 


部署一或多個以使用者為宿主的語音信箱原則是選擇性的。 如果您要部署每個使用者的原則，您必須將它們明確指派給使用者、群組或連絡人物件。

如需指派或移除依使用者託管語音信箱原則指派或移除作業的詳細資料，請參閱下列 Cmdlet 的 Lync Server 管理命令介面檔：

  - 授與 CsHostedVoicemailPolicy

  - 移除-CsHostedVoicemailPolicy

## <a name="to-assign-a-per-user-hosted-voice-mail-policy"></a>指派每位使用者託管的語音信箱原則

1.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  執行授與 CsHostedVoicemailPolicy Cmdlet，將每位使用者託管的語音信箱原則指派給個別的使用者、群組和連絡人物件。 例如，執行：
    
        Grant-CsHostedVoicemailPolicy -Identity "Ken Myer" -PolicyName ExRedmond
    
    這個範例已將 ExRedmond 託管的語音信箱原則指派給使用者 Ken Myer。
    
    身分**識別**指定要修改的使用者帳戶。 身分識別值可以使用下列任何一種格式加以指定：
    
      - 使用者的 SIP 位址
    
      - 使用者的 Active Directory 使用者主要名稱
    
      - 使用者的網域\\登入名稱（例如 contoso\\kenmyer）
    
      - 使用者的 Active Directory 網域服務顯示名稱（例如，Ken Myer）。 如果使用顯示名稱作為身分識別值，您可以使用星號（\*）萬用字元。 例如，恒等 "\* smith" 會傳回其顯示名稱以字串值 "smith" 結尾的所有使用者。
    

    > [!NOTE]  
    > 使用者的 Active Directory SAM-帳戶名稱不能用來做為身分識別值，因為 SAM-帳戶名稱在林中不一定是唯一的。


