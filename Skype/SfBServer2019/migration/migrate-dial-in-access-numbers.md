---
title: 移轉撥入存取號碼
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 若要將撥入存取號碼遷移至商務用 Skype Server 2019，必須執行 Move-CsApplicationEndpoint Cmdlet 以遷移連絡人物件。 在舊版安裝和商務用 Skype Server 2019 共存期間內，您在商務用 Skype Server 2019 中建立的撥入存取號碼，會類似于您在舊版安裝中建立的撥入存取號碼，如本節所述。
ms.openlocfilehash: a65f0252dd4899ef196701d282a1b14673c5c22b7851029b35a15c4685c2b28d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54318048"
---
# <a name="migrate-dial-in-access-numbers"></a>移轉撥入存取號碼

若要將撥入存取號碼遷移至商務用 Skype Server 2019，必須執行 **Move-CsApplicationEndpoint** Cmdlet 以遷移連絡人物件。 在舊版安裝和商務用 Skype Server 2019 共存期間內，您在商務用 Skype Server 2019 中建立的撥入存取號碼，會類似于您在舊版安裝中建立的撥入存取號碼，如本節所述。 

您在舊版安裝中建立但移至商務用 Skype Server 2019 的撥入存取號碼，或是在遷移之前、期間或之後于商務用 Skype Server 2019 中建立的撥入存取號碼，都具有下列特性：

- 不會出現在 Office 通訊伺服器 2007 R2 會議邀請和撥入存取號碼頁面上。

- 會出現在舊版安裝會議邀請和撥入存取號碼頁面上。

- 會出現在商務用 Skype Server 2019 會議邀請和撥入存取號碼頁面上。

- 無法在 Office 通訊伺服器 2007 R2 系統管理工具中查看或修改。

- 可在舊版安裝控制台和舊版安裝管理命令介面中查看及修改。

- 可在商務用 Skype Server 2019 控制台和商務用 Skype Server 2019 管理命令介面中查看及修改。

- 可以使用具有 Priority 參數的 Set-CsDialinConferencingAccessNumber Cmdlet，在地區內重新排序。

您必須完成將指向舊版安裝集區的撥入存取號碼遷移，再解除委任舊版安裝集區。 如果您未完成撥入存取號碼遷移（如下列程式所述），則對存取號碼的來電將會失敗。

> [!IMPORTANT]
> 您必須先執行此程式，再解除委任舊版安裝集區。 

> [!NOTE]
> 建議您在網路使用量很低時移動撥入存取號碼，以防出現短時間的服務中斷。 

## <a name="to-identify-and-move-dial-in-access-numbers"></a>識別並移動撥入存取號碼

1. 啟動商務用 Skype Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[ **Microsoft 商務用 Skype Server 2019**]，然後按一下 [**商務用 Skype Server 管理命令** 介面]。

2. 若要將每個撥入存取號碼移至主控于商務用 Skype Server 2019 的集區，請從命令列執行： 

   ```PowerShell
   Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>
   ```

3. 開啟商務用 Skype Server 控制台]。

4. 在左側導覽列中，按一下 **[會議]**。

5. 按一下 [ **撥入存取號碼** ] 索引標籤。 

6. 確認您要遷移之舊版安裝集區的撥入存取號碼仍未保留。

    > [!NOTE]
    > 當所有撥入存取號碼指向商務用 Skype Server 2019 集區時，即可解除委任舊版安裝集區。 

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-control-panel"></a>使用商務用 Skype Server 控制台驗證撥入存取號碼遷移

1. 從指派給 **CsUserAdministrator** 角色或 **CsAdministrator** 角色的使用者帳戶，登入內部部署中的任何電腦。 

2. 開啟商務用 Skype Server 控制台]。

3. 在左側導覽列中，按一下 **[會議]**。

4. 按一下 [ **撥入存取號碼** ] 索引標籤。 

5. 確認所有撥入存取號碼都已遷移到主控于商務用 Skype Server 2019 的集區。

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-management-shell"></a>使用商務用 Skype Server 管理命令介面來驗證撥入存取號碼遷移

1. 開啟商務用 Skype Server 管理命令介面。

2. 若要傳回已遷移的所有電話撥入式會議存取號碼，請從命令列執行：

   ```PowerShell
   Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}
   ```

3. 確認所有撥入存取號碼都已遷移到主控于商務用 Skype Server 2019 的集區。


