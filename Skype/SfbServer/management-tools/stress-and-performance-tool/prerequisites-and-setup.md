---
title: Skype for Busines 應力和效能工具的必要條件和設定
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 商務用 Skype Server 2015 應力和效能工具的需求或必要條件。 如何安裝或設定壓力和效能工具。
ms.openlocfilehash: a58eb5e291878bea74365cd1b9519983c7a77a84
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814953"
---
# <a name="prerequisites-and-setup-for-the-skype-for-busines-stress-and-performance-tool"></a>Skype for Busines 應力和效能工具的必要條件和設定
 
商務用 Skype Server 2015 應力和效能工具的需求或必要條件。 如何安裝或設定壓力和效能工具。
  
在執行壓力和效能工具之前，我們有下列幾節需要注意的硬體、軟體和系統設定需求：
  
- [用戶端硬體需求](prerequisites-and-setup.md#ClientHardwareReqs)
    
- [用戶端軟體需求](prerequisites-and-setup.md#ClientSoftwareReqs)
    
- [設定需求](prerequisites-and-setup.md#ConfigReqs)
    
此外，我們還提供下列章節，以供 [安裝商務用 Skype Server 2015 應力和效能工具](prerequisites-and-setup.md#Installing)
  
## <a name="client-hardware-requirements"></a>用戶端硬體需求
<a name="ClientHardwareReqs"> </a>

針對您的商務用 Skype Server 2015 部署執行壓力和效能工具時，您至少需要滿足測試中每個4500使用者的下列硬體需求：
  
- 1 gb 網路介面卡
    
- 8 GB RAM
    
- 2顆雙核 CPUs
    
## <a name="client-software-requirements"></a>用戶端軟體需求
<a name="ClientSoftwareReqs"> </a>

壓力和效能工具支援的作業系統如下：
  
- Windows Server 2012
    
- Windows Server 2008 (64-位) 
    
此外，電腦必須滿足下列軟體需求：
  
- 您將需要安裝 Microsoft .NET 4.5 Framework。 [在這裡下載 .Net 4.5 Framework。](https://www.microsoft.com/download/details.aspx?id=30653)
    
- 您將需要 Windows 中啟用的桌面體驗功能。
    
- 您將需要安裝 Microsoft Visual c + + 2013 (x64) 。 [在這裡下載 Visual c + + 2013](https://www.microsoft.com/download/details.aspx?id=40784)
    
- 您即將成功部署商務用 Skype Server 2015。
    
## <a name="configuration-requirements"></a>設定需求
<a name="ConfigReqs"> </a>

您將需要進行下列額外設定，以順利執行壓力和效能工具：
  
- 您必須以網域或本機管理員群組成員的身分登入伺服器。
    
- 您無法在使用者帳戶所在的任何前端伺服器或 Standard Edition server 上安裝商務用 Skype Server 2015 使用者建立工具 ( # A0) 。
    
- 當使用者建立工具多次執行時，每個啟用 Microsoft 整合通訊的使用者都必須有唯一的電話號碼。
    
- 頁面檔案大小應是系統管理的，否則至少必須是電腦系統中 RAM 的記憶體量的1.5 倍。
    
## <a name="installing-the-skype-for-business-server-2015-stress-and-performance-tool"></a>安裝商務用 Skype Server 2015 應力和效能工具
<a name="Installing"> </a>

安裝會變得更簡單。 您必須在您要用來模擬使用者流量的每一部用戶端電腦上，，在您要建立使用者和連絡人的每個集區的前端伺服器上執行 Windows Installer 檔案（ **CapacityPlanningTool.msi**）。
  
若要下載 .msi，以及其他文章中提及的範例腳本，請移至 [下載中心] 連結：商務用 [Skype Server 2015、壓力和效能工具](https://www.microsoft.com/download/details.aspx?id=50367)。
  

