---
title: 在商務用 Skype 中為使用者啟用群組呼叫挑選並指派群組號碼
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
description: 在商務用 Skype Server Enterprise Voice 中啟用群組呼叫挑選的使用者, 並指派群組號碼。
ms.openlocfilehash: 78bdd78bf7e5bb3a9438a60b54a89664d22666ee
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240613"
---
# <a name="enable-group-call-pickup-for-users-and-assign-a-group-number-in-skype-for-business"></a>在商務用 Skype 中為使用者啟用群組呼叫挑選並指派群組號碼

在商務用 Skype Server Enterprise Voice 中啟用群組呼叫挑選的使用者, 並指派群組號碼。

在您將呼叫挑選群組編號新增至 [通話駐留軌道] 表格之後, 您可以使用 SEFAUtil 工具, 將群組號碼指派給使用者, 並為他們啟用群組呼叫分揀。

> [!NOTE]
> 在混合式部署中, 請勿將群組呼叫挑選群組指派給駐留在線上的使用者。 以線上為宿主的使用者無法參與群組通話挑選。 也就是說, 其他使用者無法接聽其來電, 也無法將來電應答給其他使用者。

### <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a>指派群組號碼並為使用者啟用群組呼叫分揀

1. 以系統管理員許可權登入您安裝 SEFAUtil 工具的電腦。

2. 在命令列上執行:

   ```
   SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
   ```

    例如, 若要將群組號碼199指派給使用者:

   ```
   SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199
   ```

## <a name="see-also"></a>另請參閱

[停用群組拾取給使用者](https://technet.microsoft.com/library/91b06f9e-2840-45a2-bbb3-6a29179b9a9f.aspx)

