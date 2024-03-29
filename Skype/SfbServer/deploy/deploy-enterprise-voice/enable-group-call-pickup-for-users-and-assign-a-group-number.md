---
title: 在商務用 Skype 中為使用者啟用群組呼叫收取和指派群組號碼
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
description: 在商務用 Skype Server 企業語音中啟用群組通話收取的使用者，並指派群組號碼。
ms.openlocfilehash: 5ebb5d4f2f84133b0c226773fd71c66f687ca5f9
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62390695"
---
# <a name="enable-group-call-pickup-for-users-and-assign-a-group-number-in-skype-for-business"></a>在商務用 Skype 中為使用者啟用群組呼叫收取和指派群組號碼

在商務用 Skype Server 企業語音中啟用群組通話收取的使用者，並指派群組號碼。

在您將呼叫收取群組號碼新增至通話駐留軌道表之後，您可以使用 SEFAUtil 工具將群組號碼指派給使用者，並為其啟用群組呼叫收取。

> [!NOTE]
> 在混合式部署中，請勿將群組呼叫收取群組指派給位於線上的使用者。 線上中的使用者無法參與「群組呼叫收取」。 也就是說，其他使用者無法接聽他們的來電，也無法接聽來電給其他使用者。

### <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a>若要指派群組號碼，並為使用者啟用群組呼叫收取功能

1. 使用系統管理員權力，登入安裝 SEFAUtil 工具的電腦。

2. 在命令列中執行：

   ```console
   SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
   ```

    例如，若要將群組號碼199指派給使用者：

   ```console
   SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199
   ```

## <a name="see-also"></a>另請參閱

[停用使用者的群組收取](/previous-versions/office/lync-server-2013/lync-server-2013-disable-group-call-pickup-for-users)