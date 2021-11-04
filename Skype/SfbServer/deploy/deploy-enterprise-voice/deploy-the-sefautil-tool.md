---
title: 在商務用 Skype 中部署 SEFAUtil 工具
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
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
ms.assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
description: 在商務用 Skype Server 中部署 SEFAUtil 工具。
ms.openlocfilehash: 40f35f227a2e1753f3362cd01b29883e06e1b893
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60761531"
---
# <a name="deploy-the-sefautil-tool-in-skype-for-business"></a>在商務用 Skype 中部署 SEFAUtil 工具
 
在商務用 Skype Server 中部署 SEFAUtil 工具。
  
若要部署和管理群組呼叫收取，您必須使用商務用 Skype Server 版本的 SEFAUtil 工具。 
  
> [!IMPORTANT]
> Microsoft 整合通訊 Managed API (UCMA) 5 執行時間必須安裝在您計畫執行 SEFAUtil 工具的任何電腦上。 請在這裡下載： [整合通訊 MANAGED API 5.0 Runtime](https://www.microsoft.com/download/details.aspx?id=47344)。 您也可以下載 UCMA 5 SDK，其中包含執行時間，如下所示： [UCMA 5.0 SDK](https://www.microsoft.com/download/details.aspx?id=47345)。
  
您可以在部署中的任何前端集區中執行 SEFAUtil 工具。 若要執行 SEFAUtil 工具，您必須執行信任之應用程式電腦上的商務用 Skype 部署嚮導中的步驟1、2和3。 SEFAUtil 需要有本機設定存放區，以及憑證。
  
> [!NOTE]
> 如需有關執行 SEFAUtil 的詳細資訊，請參閱博客文章：「[如何取得 SEFAUtil 執行？](/archive/blogs/jenstr/how-to-get-sefautil-running)」。 
  
### <a name="to-deploy-sefautil"></a>若要部署 SEFAUtil

1. 以 **委派安裝許可權** 中所述，以 RTCUniversalServerAdmins 群組成員的身分或必要使用者權限的方式，登入安裝商務用 Skype Server 管理命令介面的電腦。
    
2. 啟動商務用 Skype Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[**商務用 Skype 2015**]，然後按一下 [**商務用 Skype Server 管理命令** 介面]。
    
3. SEFAUtil 工具只能在屬於受信任應用程式集區一部分的電腦上執行。 如有需要，針對您計畫執行 SEFAUtil 的前端集區定義信任的應用程式集區。 在命令列中執行：
    
   ```powershell
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```
    > [!NOTE]
    > 集區 FQDN：將主控 SEFAUtil 應用程式之伺服器或集區的 fqdn (通常是商務用 Skype 前端伺服器或集區) 。
    > 集區報名者 fqdn：與此應用程式集區關聯的商務用 Skype 前端伺服器或集區的 FQDN。
    > 集區網站：此集區所在之網站的網站識別碼。

4. 將 SEFAUtil 工具定義為信任的應用程式。 在命令列中執行：
    
   ```powershell
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
   ```

    > [!NOTE]
    > 如有需要，您可以使用不同的埠。 
  
5. 使用您的變更來啟用拓撲。 在命令列中執行：
    
   ```powershell
   Enable-CsTopology
   ```

6. 若尚未從[這個位置](https://www.microsoft.com/download/details.aspx?id=52631)下載 SEFAUtil 工具的商務用 Skype Server 版本，請將其安裝在您在步驟3中建立的受信任應用程式集區。
    
7. 請確認 SEFAUtil 工具是否運作正常，如下所示： 
    
    a. 從 Windows 命令提示字元中，使用管理員許可權執行工具，以顯示部署中使用者的來電轉接設定。
    
    b. 顯示使用者的「來電轉接」設定。 在命令列中執行：
    
   ```console
   SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
   ```

將會顯示使用者的「來電轉接」設定。
