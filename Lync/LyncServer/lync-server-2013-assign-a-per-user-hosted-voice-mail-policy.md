---
title: Lync Server 2013：指派每位使用者的主控語音信箱原則
description: Lync Server 2013：指派每位使用者的主控語音信箱原則。
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
ms.openlocfilehash: 071d504c452b4d3adb1b636cb5c4ff8835200107
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559889"
---
# <a name="assign-a-per-user-hosted-voice-mail-policy-in-lync-server-2013"></a>在 Lync Server 2013 中指派每位使用者的主控語音信箱原則

 


部署一或多個個別使用者主控語音信箱原則是選用的。 如果您選擇部署個別使用者原則，則必須明確指派原則給使用者、群組或連絡人物件。

如需指派或移除個別使用者主控語音信箱原則指派的詳細資訊，請參閱 Lync Server 管理命令介面檔中的下列 Cmdlet：

  - Grant-CsHostedVoicemailPolicy

  - Remove-CsHostedVoicemailPolicy

## <a name="to-assign-a-per-user-hosted-voice-mail-policy"></a>指派個別使用者主控語音信箱原則

1.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  執行 Grant-CsHostedVoicemailPolicy Cmdlet，將每位使用者的裝載語音信箱原則指派給個別使用者、群組和連絡人物件。 例如，執行：
    
        Grant-CsHostedVoicemailPolicy -Identity "Ken Myer" -PolicyName ExRedmond
    
    這個範例會將 ExRedmond 主控語音信箱原則指派給使用者 Ken Myer。
    
    **Identity** 指定要修改的使用者帳戶。 您可以使用下列任何格式指定 Identity 值：
    
      - 使用者的 SIP 位址
    
      - 使用者的 Active Directory 使用者主體名稱
    
      - 使用者的網域 \\ 登入名稱 (例如，contoso \\ kenmyer) 
    
      - 使用者的 Active Directory 網域服務 Display-Name (例如 Ken Myer) 。 如果使用 Display-Name 做為 Identity 值，您可以使用星號 (\*) 萬用字元。 例如，身分識別 " \* smith" 會傳回 Display-Name 以字串值 "smith" 結尾的所有使用者。
    

    > [!NOTE]  
    > 使用者的 Active Directory SAM 帳戶名稱不能做為身分識別值，因為 SAM 帳戶名稱在樹系中不一定是唯一的。


