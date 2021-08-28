---
title: 升級商務用 Skype Server 統計資料
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 71f5d0a0-ca81-4ac1-b590-8f854504f21f
description: 摘要：閱讀此主題以瞭解如何升級商務用 Skype Server 的統計資料管理員。
ms.openlocfilehash: caa2a5f7576a046c990315b638e618a379dd039e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58611982"
---
# <a name="upgrade-statistics-manager-for-skype-for-business-server"></a>升級商務用 Skype Server 統計資料
 
**摘要：** 閱讀此主題以瞭解如何升級商務用 Skype Server 的統計資料管理員。
  
本主題說明如何升級商務用 Skype Server 的統計資料管理員現有安裝，這是一種強大的工具，可讓您即時查看商務用 Skype Server 健康情況與效能資料。 您可以每隔幾秒輪詢每數百部伺服器上的效能資料，並在統計資料管理員網站上立即查看結果。 
  
如需有關統計資料管理員的詳細資訊，以及版本2.0 中的新功能，請參閱[規劃商務用 Skype Server 的統計資料管理員](plan.md)及[部署商務用 Skype Server 的統計資料管理員](deploy.md)。
  
有兩種升級方法：
  
- **自動升級。** 此方法使用自動腳本。 這是最簡單的方法，且應該適用于所有的升級案例。
    
- **手動升級。** 這種方法是一種備份計畫，在這種情況下，自動升級失敗的情況很少見。
    
## <a name="prerequisites"></a>必要條件

在升級之前，請確定您有下列資訊：
  
- 主動攔截器憑證指紋
    
- 在安裝監聽器及每個代理人) 時輸入的監聽器服務密碼 (
    
- 網站的 SSL 憑證設定
    
## <a name="automated-upgrade"></a>自動升級

腳本會收集您目前的憑證資訊和監聽器密碼、卸載舊版本的產品，然後安裝新版本的產品。 將不會接觸安裝在伺服器上的 Redis 實例，因此儲存在快取中的任何資料都會透過升級程式保留。
  
1. 將新版本的代理程式、監聽器和網站的 MSI 檔案，放入監聽器電腦上的單一資料夾中，同時將 Update-StatsMan.ps1 腳本。
    
2. 開啟 [管理 PowerShell] 視窗。 升級攔截器元件：
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Listener
   ```

> [!NOTE]
> 在傳送至安裝程式時，會在命令列上以純文字顯示統計資料管理員服務密碼。 請務必視需要遮罩監視器。 
  
1. 在執行腳本時，您應該會收到卸載舊版本產品的提示。 答案是。
    
2. 如果正在執行監聽器服務，系統會提示您關閉應用程式，然後再繼續進行。 允許應用程式關閉 (統計資料管理員偵聽程式服務將停止) 。
    
3. 繼續執行安裝程式。 您應該會發現服務密碼和憑證指紋已預先填入。 如果不是，請在繼續之前先新增您儲存的值。
    
4. 開啟 [管理 PowerShell] 視窗。 升級網站元件：
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Website
   ```

5. 在執行腳本時，您應該會收到卸載舊版本產品的提示。 答案是。
    
6. 如果代理程式服務正在執行，系統會提示您關閉應用程式，然後再繼續進行。 允許應用程式在 StatsMan 代理程式服務) 停止時關閉 (。
    
7. 繼續執行安裝程式。 您應該會發現服務密碼和憑證指紋已預先填入。 如果不是，請在繼續之前先新增您儲存的值。
    
8. 開啟 [管理 PowerShell] 視窗。 升級代理程式元件：
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Agent
   ```

9. 在執行腳本時，您應該會收到卸載舊版本產品的提示。 答案是。
    
10. 繼續執行安裝程式。 您應注意到網站埠已經預先填入。 如果不是，請在繼續之前先新增您儲存的值。
    
11. 使用瀏覽器驗證網站是否如預期般運作。
    
> [!NOTE]
> 代理程式升級可以搭配-NoPrompt 參數使用。 這可讓卸載/安裝程式以無訊息的方式執行，允許諸如 PSExec 之類的工具在大量的伺服器上遠端執行升級。 
  
### <a name="manual-upgrade"></a>手動升級

若由於某些原因，自動升級會失敗，您可以無條件執行手動升級，如下所示：
  
1. 在監聽器電腦上，透過「程式和功能」控制台中的 [程式和功能] 控制台卸載監聽器、網站和代理程式 () 。 
    
    > [!NOTE]
    >  保留 Redis，讓快取中的資料會透過升級程式進行維護。
  
2. 安裝新版本的元件，包括系統提示時所儲存的值。 如需安裝元件的詳細資訊，請參閱 [部署統計資料管理員](deploy.md#BKMK_Deploy)

    
## <a name="for-more-information"></a>相關資訊
<a name="BKMK_Fixed"> </a>

如需詳細資訊，請參閱下列各主題：
  
- [商務用 Skype Server 統計資料的規劃](plan.md)
    
- [部署商務用 Skype Server 統計資料](deploy.md)
    
- [疑難排解商務用 Skype Server 統計資料](troubleshoot.md)
