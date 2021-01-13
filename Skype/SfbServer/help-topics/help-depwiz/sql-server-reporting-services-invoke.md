---
title: SQL Server Reporting Services (叫用)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 在提供將監控伺服器報告部署至 Microsoft SQL Server 2008 R2 的必要資訊之後，或在 Microsoft SQL Server 2012 報表服務中，[頁面執行] 命令會顯示將報告安裝至 SQL Server Reporting Services 所發出的命令摘要。
ms.openlocfilehash: eac8b7884859c0b5b14218471054533eedb6d481
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49829533"
---
# <a name="sql-server-reporting-services-invoke"></a><span data-ttu-id="1e83c-103">SQL Server Reporting Services (叫用)</span><span class="sxs-lookup"><span data-stu-id="1e83c-103">SQL Server Reporting Services (Invoke)</span></span>
 
<span data-ttu-id="1e83c-104">在提供將監控伺服器報告部署至 Microsoft SQL Server 2008 R2 的必要資訊之後，或在 Microsoft SQL Server 2012 報表服務中，[頁面執行] 命令會顯示將報告安裝至 SQL Server Reporting Services 所發出的命令摘要。</span><span class="sxs-lookup"><span data-stu-id="1e83c-104">After supplying the required information for the deployment of the Monitoring Server reports to the Microsoft SQL Server 2008 R2, or to Microsoft SQL Server 2012 Report Services, the page Execute Commands displays a summary of commands that are issued to install the reports to the SQL Server Reporting Services.</span></span>
  
<span data-ttu-id="1e83c-p101">請檢閱命令摘要，注意命令顯示的任何錯誤或警告訊息。如果產生記錄檔，請從摘要視窗下的下拉式清單中選取記錄檔，然後按一下 [檢視記錄檔] 來顯示記錄檔。</span><span class="sxs-lookup"><span data-stu-id="1e83c-p101">Review the summary of commands and note any error or warning messages displayed from the commands. If a log file is generated, select the log file from the drop-down list under the summary window, and click **View Log** to display the log file.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="1e83c-107">若要讓 Reporting Services 報表順利部署，並在部署完成之後存取報告，您必須具備 TCP/IP 的埠 80 (（選用）、TCP 埠443（如果您將憑證指派給 Reporting) Services，則會在 SQL Server 上以 Advanced Security 的 Windows 防火牆中開啟）。</span><span class="sxs-lookup"><span data-stu-id="1e83c-107">For the Reporting Services reports to deploy successfully, and to access the reports after deployment is complete, you must have TCP/IP port 80 (and optionally, TCP port 443 for SSL, if you assign a certificate to the Reporting Services) open in the Windows Firewall with Advanced Security on the SQL Server.</span></span> <span data-ttu-id="1e83c-108">如需詳細資訊，請參閱 [設定 Windows 防火牆以允許](https://go.microsoft.com/fwlink/p/?linkId=218031) Microsoft sql Server 2008 R2 的 SQL server 存取。</span><span class="sxs-lookup"><span data-stu-id="1e83c-108">For details, see [Configure the Windows Firewall to Allow SQL Server Access](https://go.microsoft.com/fwlink/p/?linkId=218031) for Microsoft SQL Server 2008 R2.</span></span>
  
<span data-ttu-id="1e83c-109">查看摘要之後，按一下 **[完成]** ，以完成將報告安裝至 SQL Server Reporting Services。</span><span class="sxs-lookup"><span data-stu-id="1e83c-109">After reviewing the summary, click **Finish** to complete the installation of the reports to the SQL Server Reporting Services.</span></span>
  

