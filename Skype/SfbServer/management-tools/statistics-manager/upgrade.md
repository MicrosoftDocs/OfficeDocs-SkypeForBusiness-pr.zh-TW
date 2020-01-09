---
title: 升級商務用 Skype Server 統計資料
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 71f5d0a0-ca81-4ac1-b590-8f854504f21f
description: 摘要：請閱讀本主題，以瞭解如何升級商務用 Skype Server 的統計資料管理器。
ms.openlocfilehash: de88257b628256c47b68036852d82fb6715c043f
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992500"
---
# <a name="upgrade-statistics-manager-for-skype-for-business-server"></a>升級商務用 Skype Server 統計資料
 
**摘要：** 若要瞭解如何升級商務用 Skype Server 的統計資料管理員，請閱讀本主題。
  
本主題描述如何針對商務用 Skype Server 升級現有的統計資料管理員安裝，這是一種強大的工具，可讓您即時查看商務用 Skype Server 健康情況和效能資料。 您可以每隔幾秒在數百個伺服器上輪詢效能資料，並立即在統計資料管理器網站上查看結果。 
  
如需有關統計管理員及版本2.0 中新功能的詳細資訊，請參閱[規劃商務用 Skype server 的統計資料管理器](plan.md)和[部署商務用 Skype Server 的統計資料管理器](deploy.md)。
  
升級的方法有兩種：
  
- **自動升級。** 這個方法會使用自動腳本。 這是最簡單的方法，且適用于所有升級案例。
    
- **手動升級。** 此方法是在自動升級失敗的情況下以備份方案的形式提供。
    
## <a name="prerequisites"></a>先決條件

升級之前，請確定您有下列資訊：
  
- Active 監聽器憑證指紋
    
- 監聽器服務密碼（在安裝監聽器及每個代理程式時輸入）
    
- 網站的 SSL 憑證設定
    
## <a name="automated-upgrade"></a>自動升級

此腳本會收集您目前的憑證資訊和監聽器密碼、卸載舊版本的產品，然後安裝新版產品。 安裝在伺服器上的 Redis 實例不會被觸摸，因此儲存在快取中的任何資料都會透過升級程式來保留。
  
1. 針對新版的 agent、監聽器和網站，將 MSI 檔案連同 Update-StatsMan 腳本一起放在監聽器電腦上的單一資料夾中。
    
2. 開啟 [管理 PowerShell] 視窗。 升級攔截器元件：
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Listener
   ```

> [!NOTE]
> [統計資料管理器] 服務的密碼將會在傳送至安裝程式的命令列上以明文形式顯示。 視需要，請務必遮罩您的監視器。 
  
1. 在執行腳本時，系統會提示您卸載舊版本的產品。 回答 [是]。
    
2. 如果監聽器服務正在執行，系統會提示您關閉應用程式，然後再繼續進行。 允許應用程式關閉（統計管理員攔截器服務將會停止）。
    
3. 繼續執行安裝程式。 您應該注意到 [服務密碼] 和 [憑證指紋] 是預先填入的。 如果不是，請在繼續之前先加上您所儲存的值。
    
4. 開啟 [管理 PowerShell] 視窗。 升級網站元件：
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Website
   ```

5. 在執行腳本時，系統會提示您卸載舊版本的產品。 回答 [是]。
    
6. 如果代理服務正在執行，系統會提示您關閉應用程式，然後再繼續進行。 允許應用程式關閉（StatsMan 代理程式服務將停用）。
    
7. 繼續執行安裝程式。 您應該注意到 [服務密碼] 和 [憑證指紋] 是預先填入的。 如果不是，請在繼續之前先加上您所儲存的值。
    
8. 開啟 [管理 PowerShell] 視窗。 升級代理元件：
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Agent
   ```

9. 在執行腳本時，系統會提示您卸載舊版本的產品。 回答 [是]。
    
10. 繼續執行安裝程式。 您應該注意到網站埠已預先填入。 如果不是，請先新增您儲存的值，然後繼續。
    
11. 使用瀏覽器驗證網站是否如預期方式運作。
    
> [!NOTE]
> 您可以將代理升級與-NoPrompt 開關搭配使用。 這可讓卸載/安裝程式以無訊息方式執行，允許諸如 PSExec 之類的工具在大量的伺服器上遠端執行升級。 
  
### <a name="manual-upgrade"></a>手動升級

如果由於某種原因，自動升級失敗，您可以隨時執行手動升級，如下所示：
  
1. 在監聽器電腦上，透過 [程式和功能] 控制台卸載監聽器、網站和 Agent （如果它是安裝在此伺服器上）。 
    
    > [!NOTE]
    >  保持 Redis 已安裝，以讓快取中的資料能夠透過升級程式維護。
  
2. 安裝新的元件版本，包括您在系統提示時所儲存的值。 如需安裝元件的詳細資訊，請參閱[部署統計資料管理器](deploy.md#BKMK_Deploy)

    
## <a name="for-more-information"></a>如需詳細資訊
<a name="BKMK_Fixed"> </a>

如需詳細資訊，請參閱下列內容：
  
- [商務用 Skype Server 統計資料的規劃](plan.md)
    
- [部署商務用 Skype Server 統計資料](deploy.md)
    
- [疑難排解商務用 Skype Server 統計資料](troubleshoot.md)
