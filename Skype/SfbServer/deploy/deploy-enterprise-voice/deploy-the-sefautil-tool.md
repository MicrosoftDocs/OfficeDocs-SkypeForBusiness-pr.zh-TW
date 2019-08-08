---
title: 在商務用 Skype 中部署 SEFAUtil 工具
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
ms.assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
description: 在商務用 Skype Server 中部署 SEFAUtil 工具。
ms.openlocfilehash: 1721f4d611a08a3054366e36b0ec9a3ebccf6c78
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36245780"
---
# <a name="deploy-the-sefautil-tool-in-skype-for-business"></a>在商務用 Skype 中部署 SEFAUtil 工具
 
在商務用 Skype Server 中部署 SEFAUtil 工具。
  
若要部署及管理群組呼叫, 您必須使用商務用 Skype Server 版本的 SEFAUtil 工具。 
  
> [!IMPORTANT]
> Microsoft 整合通訊管理 API (UCMA): 必須在您打算執行 SEFAUtil 工具的任何電腦上安裝5個執行時間。 請在這裡下載:[整合通訊管理 API 5.0 運行](https://www.microsoft.com/en-us/download/details.aspx?id=47344)時間。 您也可以下載 UCMA 5 SDK (包括執行時間), 如下所示: [UCMA 5.0 SDK](https://www.microsoft.com/en-us/download/details.aspx?id=47345)。
  
您可以在部署的任何前端池中執行 SEFAUtil 工具。 若要執行 SEFAUtil 工具, 您必須在受信任的應用程式電腦上, 從商務用 Skype 部署嚮導執行步驟1、2和3。 SEFAUtil 需要有本機配置存放區, 以及認證。
  
> [!NOTE]
> 如需執行 SEFAUtil 的詳細資訊, 請參閱博客文章: 「[如何取得 SEFAUtil 執行？](https://go.microsoft.com/fwlink/?LinkId=278940)」。 
  
### <a name="to-deploy-sefautil"></a>若要部署 SEFAUtil

1. 登入商務用 Skype Server Management Shell 的電腦是以 RTCUniversalServerAdmins 群組的成員或必要的使用者權利來安裝, 如**委派設定許可權**中所述。
    
2. 啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype 2015**], 然後按一下 [**商務用 skype Server management Shell**]。
    
3. SEFAUtil 工具只能在屬於受信任的應用程式池的電腦上執行。 如有需要, 請為您打算執行 SEFAUtil 的前端池定義受信任的應用程式池。 在命令列上執行:
    
   ```
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```
    > [!NOTE]
    > [池 FQDN]: 將裝載 SEFAUtil 應用程式的伺服器或池的 FQDN (通常是商務用 Skype 前端伺服器或池)。
    > Pool 註冊機構 FQDN: 與此應用程式池關聯的商務用 Skype 前端伺服器或池的 FQDN。
    > [文件庫網站]: 此池所駐留的網站的 [網站識別碼]。

4. 將 SEFAUtil 工具定義為受信任的應用程式。 在命令列上執行:
    
   ```
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
   ```

    > [!NOTE]
    > 如有需要, 您可以使用不同的埠。 
  
5. 使用您的變更啟用拓撲。 在命令列上執行:
    
   ```
   Enable-CsTopology
   ```

6. 如果您還沒有從[這個位置](https://www.microsoft.com/en-us/download/details.aspx?id=52631)下載 SEFAUtil 工具的商務用 Skype Server 版本, 請將它安裝在您在步驟3所建立的信任應用程式池中。
    
7. 確認 SEFAUtil 工具正常運作, 如下所示: 
    
    是. 從具有系統管理員許可權的 Windows 命令提示字元執行該工具, 以在您的部署中顯示使用者的來電轉接設定。
    
    乙. 顯示使用者的 [來電轉接] 設定。 在命令列上執行:
    
   ```
   SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
   ```

隨即會顯示使用者的 [來電轉接] 設定。
    

