---
title: 遷移撥入存取號碼
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 將撥入存取號碼移植到商務用 Skype Server 2019 需要執行 CsApplicationEndpoint Cmdlet 來遷移連絡人物件。 在舊版安裝與商務用 Skype Server 2019 的共存期間, 您在商務用 Skype Server 2019 中建立的撥入存取號碼與您在舊版安裝中建立的撥入存取號碼類似, 如以下所述。頂部.
ms.openlocfilehash: 83cf8b75bcf9a8d4794ae0f95962f3627d8592c1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189076"
---
# <a name="migrate-dial-in-access-numbers"></a>遷移撥入存取號碼

將撥入存取號碼移植到商務用 Skype Server 2019 需要執行**CsApplicationEndpoint** Cmdlet 來遷移連絡人物件。 在舊版安裝與商務用 Skype Server 2019 的共存期間, 您在商務用 Skype Server 2019 中建立的撥入存取號碼與您在舊版安裝中建立的撥入存取號碼類似, 如以下所述。頂部. 

您在舊版安裝中建立的撥入號碼, 但移動到商務用 Skype Server 2019, 或是在遷移期間或之後在商務用 Skype Server 2019 中建立的電話, 都具有下列特性:

- 不會出現在 Office 通訊伺服器 2007 R2 會議邀請和 [撥入存取號碼] 頁面上。

- 出現在舊版 [安裝會議邀請] 和 [撥入存取號碼] 頁面上。

- 出現在商務用 Skype Server 2019 會議邀請和撥入存取號碼頁面上。

- 無法在 Office 通訊伺服器 2007 R2 管理工具中查看或修改。

- 您可以在舊版安裝控制台和舊版安裝管理命令介面中查看和修改。

- 您可以在商務用 Skype Server 2019 [控制台] 和商務用 Skype Server 2019 管理命令介面中查看及修改。

- 可在區域內使用 CsDialinConferencingAccessNumber Cmdlet 與 Priority 參數重新排序。

您必須先完成指向舊版安裝池中的撥入存取號碼的遷移, 才能停止舊版安裝區。 如果您沒有完成撥入存取號碼遷移, 請參閱以下程式中所述的接入號碼來電將會失敗。

> [!IMPORTANT]
> 您必須先執行此程式, 然後才能解除舊版安裝池。 

> [!NOTE]
> 我們建議您在網路使用量較低時移動撥入存取號碼 (如果有短暫的服務停機時間)。 

## <a name="to-identify-and-move-dial-in-access-numbers"></a>識別及移動撥入存取號碼

1. 啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [ **Microsoft 商務用 skype server 2019**], 然後按一下 [**商務用 skype server 管理命令**介面]。

2. 若要將每個撥入存取號碼移至託管于商務用 Skype Server 2019 的 pool, 請從命令列執行: 

   ```
   Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>
   ```

3. 開啟商務用 Skype Server 的 [控制台]。

4. 在左側導覽列中, 按一下 [**會議**]。

5. 按一下 [**撥入存取號碼**] 索引標籤。 

6. 確認您要從中遷移的舊版安裝池中仍沒有任何撥入存取號碼。

    > [!NOTE]
    > 當所有撥入存取號碼都指向商務用 Skype Server 2019 池時, 您就可以開始解除舊版安裝區。 

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-control-panel"></a>使用商務用 Skype Server [控制台] 驗證撥入存取號碼遷移

1. 從指派給**CsUserAdministrator**角色或**CsAdministrator**角色的使用者帳戶登入內部部署中的任何電腦。 

2. 開啟商務用 Skype Server 的 [控制台]。

3. 在左側導覽列中, 按一下 [**會議**]。

4. 按一下 [**撥入存取號碼**] 索引標籤。 

5. 確認所有撥入存取號碼都已遷移至託管于商務用 Skype Server 2019 的池中。

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-management-shell"></a>使用商務用 Skype Server Management Shell 來驗證撥入存取號碼遷移

1. 開啟商務用 Skype Server 管理命令介面。

2. 若要從命令列中傳回已轉移的所有電話撥入式會議存取電話號碼, 請執行下列動作:

   ```
   Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}
   ```

3. 確認所有撥入存取號碼都已遷移至託管于商務用 Skype Server 2019 的池中。


