---
title: SQL Server Reporting Services (叫用)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeploySSRSInvoke
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4a4ba8d6-ba43-45b3-b834-372d092561e7
description: 在針對將監視伺服器報告部署到 Microsoft SQL Server 2008 R2 或 Microsoft SQL Server 2012 報表服務提供所需的資訊後，[執行] 命令會顯示已發出的命令摘要，以安裝向 SQL Server Reporting Services 報告。
ms.openlocfilehash: ba0b1b70d3dc1d0dbcc68931fc8bf601b7693efd
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41823337"
---
# <a name="sql-server-reporting-services-invoke"></a><span data-ttu-id="86c53-103">SQL Server Reporting Services (叫用)</span><span class="sxs-lookup"><span data-stu-id="86c53-103">SQL Server Reporting Services (Invoke)</span></span>
 
<span data-ttu-id="86c53-104">在針對將監視伺服器報告部署到 Microsoft SQL Server 2008 R2 或 Microsoft SQL Server 2012 報表服務提供所需的資訊後，[執行] 命令會顯示已發出的命令摘要，以安裝向 SQL Server Reporting Services 報告。</span><span class="sxs-lookup"><span data-stu-id="86c53-104">After supplying the required information for the deployment of the Monitoring Server reports to the Microsoft SQL Server 2008 R2, or to Microsoft SQL Server 2012 Report Services, the page Execute Commands displays a summary of commands that are issued to install the reports to the SQL Server Reporting Services.</span></span>
  
<span data-ttu-id="86c53-p101">請檢閱命令摘要，注意命令顯示的任何錯誤或警告訊息。如果產生記錄檔，請從摘要視窗下的下拉式清單中選取記錄檔，然後按一下 [檢視記錄檔] \*\*\*\* 來顯示記錄檔。</span><span class="sxs-lookup"><span data-stu-id="86c53-p101">Review the summary of commands and note any error or warning messages displayed from the commands. If a log file is generated, select the log file from the drop-down list under the summary window, and click **View Log** to display the log file.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="86c53-107">若要讓 Reporting Services 報表順利部署，且在部署完成後存取報表，您必須具備 TCP/IP 埠 80 443 （如果您是將憑證指派給 Reporting Services），請在 SQL Server 上以高級安全性在 Windows 防火牆中開啟。</span><span class="sxs-lookup"><span data-stu-id="86c53-107">For the Reporting Services reports to deploy successfully, and to access the reports after deployment is complete, you must have TCP/IP port 80 (and optionally, TCP port 443 for SSL, if you assign a certificate to the Reporting Services) open in the Windows Firewall with Advanced Security on the SQL Server.</span></span> <span data-ttu-id="86c53-108">如需詳細資訊，請參閱[將 Windows 防火牆設定為允許](https://go.microsoft.com/fwlink/p/?linkId=218031)Microsoft sql Server 2008 R2 的 SQL server 存取。</span><span class="sxs-lookup"><span data-stu-id="86c53-108">For details, see [Configure the Windows Firewall to Allow SQL Server Access](https://go.microsoft.com/fwlink/p/?linkId=218031) for Microsoft SQL Server 2008 R2.</span></span>
  
<span data-ttu-id="86c53-109">檢查摘要之後，按一下 **[完成]** 以完成報表安裝至 SQL Server Reporting Services。</span><span class="sxs-lookup"><span data-stu-id="86c53-109">After reviewing the summary, click **Finish** to complete the installation of the reports to the SQL Server Reporting Services.</span></span>
  

