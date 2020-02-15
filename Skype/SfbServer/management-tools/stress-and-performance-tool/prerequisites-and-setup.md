---
title: 必要條件和設定用於商務用 Skype Busines 壓力及效能工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 12/20/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 948c176c-75ce-418d-891a-a68427d61e40
description: 需求或 Skype for Business Server 2015 壓力及效能工具的必要條件。 如何安裝或設定 [壓力及效能工具。
ms.openlocfilehash: 9389feedb21948604b1ea68319c5fc068a561679
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "42005978"
---
# <a name="prerequisites-and-setup-for-the-skype-for-busines-stress-and-performance-tool"></a>必要條件和設定用於商務用 Skype Busines 壓力及效能工具
 
需求或 Skype for Business Server 2015 壓力及效能工具的必要條件。 如何安裝或設定 [壓力及效能工具。
  
我們有您需要留意之前執行壓力及效能工具的硬體、 軟體和系統組態需求的下列小節：
  
- [用戶端的硬體需求](prerequisites-and-setup.md#ClientHardwareReqs)
    
- [用戶端軟體需求](prerequisites-and-setup.md#ClientSoftwareReqs)
    
- [組態需求](prerequisites-and-setup.md#ConfigReqs)
    
此外，我們也有以下區段[安裝 Skype for Business Server 2015 壓力及效能工具](prerequisites-and-setup.md#Installing)
  
## <a name="client-hardware-requirements"></a>用戶端的硬體需求
<a name="ClientHardwareReqs"> </a>

當您用 Skype Server 2015 部署執行壓力及效能工具，您，在最低限度下，必須符合您的測試中每個 4500 使用者這些硬體需求：
  
- 1gb 網路介面卡
    
- 8 GB RAM
    
- 2 顆雙核心 Cpu
    
## <a name="client-software-requirements"></a>用戶端軟體需求
<a name="ClientSoftwareReqs"> </a>

支援的作業系統壓力及效能工具包括：
  
- Windows Server 2012
    
- Windows Server 2008 （64 位元）
    
此外，電腦必須符合下列軟體需求：
  
- 您必須安裝 Microsoft.NET 4.5 架構。 [下載.Net 4.5 以下架構。](https://www.microsoft.com/download/details.aspx?id=30653)
    
- 您必須在 Windows 中啟用桌面體驗功能。
    
- 您將需要 Microsoft Visual c + + 2013 (x64) 安裝。 [在這裡下載 Visual c + + 2013](https://www.microsoft.com/download/details.aspx?id=40784)
    
- 您要需要用 Skype Server 2015 成功部署。
    
## <a name="configuration-requirements"></a>組態需求
<a name="ConfigReqs"> </a>

您將需要這些額外的組態，為了順利執行壓力及效能工具：
  
- 您要的網域或本機系統管理員群組成員身分登入伺服器。
    
- 您無法安裝 Skype for Business Server 2015 使用者建立工具 (UserProvisioningTool.exe) 上的使用者帳戶所在的任何前端伺服器或 Standard Edition server。
    
- 當使用者建立工具會執行多次時，每個已啟用 Microsoft 整合通訊的使用者必須有唯一的電話號碼。
    
- 分頁檔案大小應系統管理或否則您必須是至少 1.5 倍 RAM 的數量電腦系統中。
    
## <a name="installing-the-skype-for-business-server-2015-stress-and-performance-tool"></a>安裝 Skype for Business Server 2015 壓力及效能工具
<a name="Installing"> </a>

安裝無法比較簡單。 您必須執行 Windows Installer 檔案， **CapacityPlanningTool.msi**，每個您要用於模擬使用者流量，並在每個前端伺服器集區您將在其中建立使用者與連絡人的用戶端電腦上。
  
若要下載.msi，以及我們其他文章所述的範例指令碼中，移至下載中心連結：[商務用 Skype Server 2015、 壓力及效能工具](https://www.microsoft.com/download/details.aspx?id=50367)。
  

