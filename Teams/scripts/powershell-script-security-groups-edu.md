---
title: PowerShell 腳本範例-建立學校教師與學生的安全性群組
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: angch
ms.service: msteams
audience: admin
description: 使用這個 PowerShell 腳本來建立管理學校中教師與學生的小組原則所需的安全性群組。
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 4b468ae05139571f395962b96f2963c7bb77b2e6
ms.sourcegitcommit: dc3e8ae454c42981f037f4de2e48005428b6078e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/31/2020
ms.locfileid: "46534071"
---
# <a name="powershell-script-sample---create-security-groups-for-educators-and-students-in-your-school"></a><span data-ttu-id="e5ba9-103">PowerShell 腳本範例-建立學校教師與學生的安全性群組</span><span class="sxs-lookup"><span data-stu-id="e5ba9-103">PowerShell script sample - Create security groups for educators and students in your school</span></span>

<span data-ttu-id="e5ba9-104">使用此 PowerShell 腳本，建立您在學校中管理 Microsoft 團隊原則所需的安全性群組。</span><span class="sxs-lookup"><span data-stu-id="e5ba9-104">Use this PowerShell script to create the security groups that you need to manage Microsoft Teams policies in your school.</span></span> <span data-ttu-id="e5ba9-105">[小組中的[原則指派群組](../assign-policies.md#assign-a-policy-to-a-group)] 功能可讓您將原則指派給使用者群組，例如安全性群組。</span><span class="sxs-lookup"><span data-stu-id="e5ba9-105">The [policy assignment to groups](../assign-policies.md#assign-a-policy-to-a-group) feature in Teams lets you assign a policy to a group of users, such as a security group.</span></span> <span data-ttu-id="e5ba9-106">原則指派會根據優先順序規則傳播到群組的成員。</span><span class="sxs-lookup"><span data-stu-id="e5ba9-106">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="e5ba9-107">在群組中新增或移除成員時，系統會據此更新其繼承的原則分派。</span><span class="sxs-lookup"><span data-stu-id="e5ba9-107">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="e5ba9-108">這個 PowerShell 腳本會根據授權類型，建立兩個安全性群組，其中一個適用于教職員工和教育版，另一個用於學校的學生。</span><span class="sxs-lookup"><span data-stu-id="e5ba9-108">This PowerShell script creates two security groups, one for staff and educators and another for students in your school, based on license type.</span></span> <span data-ttu-id="e5ba9-109">然後，您可以將原則指派給您建立的安全性群組。</span><span class="sxs-lookup"><span data-stu-id="e5ba9-109">You can then assign policies to the security groups that you created.</span></span> <span data-ttu-id="e5ba9-110">如需使用此腳本的詳細資訊，請參閱[在學校將原則指派給大型使用者組](../batch-group-policy-assignment-edu.md)。</span><span class="sxs-lookup"><span data-stu-id="e5ba9-110">For more information about using this script, see [Assign policies to large sets of users in your school](../batch-group-policy-assignment-edu.md).</span></span>

<span data-ttu-id="e5ba9-111">此腳本會執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="e5ba9-111">This script does the following:</span></span>

- <span data-ttu-id="e5ba9-112">識別獲指派教職員 SKU、建立安全性群組，然後將員工與教職員加入群組的人員和教育者。</span><span class="sxs-lookup"><span data-stu-id="e5ba9-112">Identifies staff and educators who are assigned a Faculty SKU, creates a security group, and then adds staff and educators  to the group.</span></span>
- <span data-ttu-id="e5ba9-113">找出指派給學生 SKU 的學生、建立安全性群組，然後將學生新增至群組。</span><span class="sxs-lookup"><span data-stu-id="e5ba9-113">Identifies students who are assigned a Student SKU, creates a security group, and then adds the students to the group.</span></span>
- <span data-ttu-id="e5ba9-114">根據使用者是否有授權，更新每個安全性群組的成員資格來新增或移除人員、教育者和學生。</span><span class="sxs-lookup"><span data-stu-id="e5ba9-114">Updates the membership of each security group to add or remove staff, educators, and students based on whether they have a license.</span></span>

<span data-ttu-id="e5ba9-115">您必須定期執行此腳本，以讓安全性群組保持在最新，且為最新狀態。</span><span class="sxs-lookup"><span data-stu-id="e5ba9-115">You'll need to run this script regularly to keep the security groups fresh and up to date.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e5ba9-116">在將原則指派給群組時，請務必瞭解[優先順序規則](../assign-policies.md#precedence-rules)與[群組指派的排名](../assign-policies.md#group-assignment-ranking)。</span><span class="sxs-lookup"><span data-stu-id="e5ba9-116">It's important to understand [precedence rules](../assign-policies.md#precedence-rules) and [group assignment ranking](../assign-policies.md#group-assignment-ranking) when assigning policies to groups.</span></span> <span data-ttu-id="e5ba9-117">請務必閱讀並瞭解[關於群組原則指派所需瞭解](../assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups)的概念。</span><span class="sxs-lookup"><span data-stu-id="e5ba9-117">Make sure that you read and understand the concepts in [What you need to know about policy assignment to groups](../assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups).</span></span>

## <a name="before-you-start"></a><span data-ttu-id="e5ba9-118">開始之前</span><span class="sxs-lookup"><span data-stu-id="e5ba9-118">Before you start</span></span>

<span data-ttu-id="e5ba9-119">下載並安裝[商務用 Skype Online PowerShell 模組](https://www.microsoft.com/download/details.aspx?id=39366)，然後在出現提示時重新開機電腦。</span><span class="sxs-lookup"><span data-stu-id="e5ba9-119">Download and install the [Skype for Business Online PowerShell module](https://www.microsoft.com/download/details.aspx?id=39366), and then restart your computer if prompted.</span></span>

<span data-ttu-id="e5ba9-120">若要進一步瞭解，請參閱使用 Office 365 PowerShell 與[團隊 powershell 概述](../teams-powershell-overview.md)[管理商務用 Skype Online](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell) 。</span><span class="sxs-lookup"><span data-stu-id="e5ba9-120">To lean more, see [Manage Skype for Business Online with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell) and [Teams PowerShell overview](../teams-powershell-overview.md).</span></span>


## <a name="sample-script"></a><span data-ttu-id="e5ba9-121">範例腳本</span><span class="sxs-lookup"><span data-stu-id="e5ba9-121">Sample script</span></span>

```powershell
<#
Script Name:
CreateOrUpdate_SecurityGroup_Per_LicenseType.ps1
Synopsis:
This script is designed to perform following operations:
1. Create a security group for faculty and student members based on the assigned license SKU and add the members accordingly.
2. Update the security group to add/remove teachers and students so that only users who have a valid teacher/student license are present in the group.
The output of the script is written in a log file present at location: C:\results\log.txt
Written By: 
Mihir Roy
Change Log:
Version 1.0, 10/08/2019 - First Draft
#>

#Figure out to determine if the user is using an existing group or creating a new one
param
(
    [string]$teachergroupname,
    [string]$teachergroupdesc,
    [string]$studentgroupname,
    [string]$studentgroupdesc,
    [Guid]$facultyid,
    [Guid]$studentid
)

[bool] $create = $false

if ([string]::IsNullOrEmpty($teachergroupname) -and [string]::IsNullOrEmpty($studentgroupname) -and [string]::IsNullOrEmpty($studentid) -and [string]::IsNullOrEmpty($facultyid)) {
    throw "Please enter valid groupnames to create groups for Teachers and Students. In order to update a group, please enter the teacher and/or student group id's."
}

#Connect to Azure AD
Write-Host "`n"
Write-Host -ForegroundColor Green "Please enter your Global Administrator Username and Password"
Write-Host "`n"
Connect-MsolService

[Guid] $teachergroupid = New-Guid
[Guid] $studentgroupid = New-Guid

if (![string]::IsNullOrEmpty($teachergroupname)) {
    New-MsolGroup -DisplayName $teachergroupname -Description $teachergroupdesc
    $Group = Get-MsolGroup -SearchString $teachergroupname
    $teachergroupid = $Group.ObjectId
    $create = $true
}

if (![string]::IsNullOrEmpty($studentgroupname)) {
    New-MsolGroup -DisplayName $studentgroupname -Description $studentgroupdesc
    $Group = Get-MsolGroup -SearchString $studentgroupname
    $studentgroupid = $Group.ObjectId
    $create = $true
}


#Build the Students Array
$StudentsArray = @()

#Build the Teachers Array
$TeachersArray = @()

#Build the Student Sku Array
$StudentSkus = @()
$AllSkus = Get-AzureADSubscribedSku
$StudentSkuIDs = ($AllSkus | ? {$_.skupartnumber -like "*student*"}).skuid
Write-Host -ForegroundColor Green "The Student Skus identified are listed below:"
Foreach ($Element in $StudentSkuIDs) {
$SkuPart = (Get-AzureADSubscribedSku | ? {$_.SkuID -eq $Element}).SkuPartNumber
Write-Host -ForegroundColor Green "Student SkuID ${Element} for License $SkuPart"
}
Write-Host "`n"

#Build the Teacher Sku Array
$TeacherSkus = @()
$AllSkus = Get-AzureADSubscribedSku
$TeacherSkuIDs = ($AllSkus | ? {$_.skupartnumber -like "*faculty*"}).skuid
Write-Host -ForegroundColor Green "The Teacher Skus identified are listed below:"
Foreach ($Element in $TeacherSkuIDs) {
$SkuPart = (Get-AzureADSubscribedSku | ? {$_.SkuID -eq $Element}).SkuPartNumber
Write-Host -ForegroundColor Green "Teacher SkuID ${Element} for License $SkuPart"
}
Write-Host "`n"

#Get All Users in AAD
Write-Host -ForegroundColor Green "Getting All Users in Azure Active Directory with an assigned license"
Write-Host "`n"
$AllUsers = Get-AzureADUser -All $true | ? {$_.AssignedLicenses -ne $null}

$teacherAdd = $create -and ($teachergroupid -ne $null)
$studentAdd = $create -and ($studentgroupid -ne $null)

#Start foreach loop for all users with student licenses
if ($teacherAdd -or $studentAdd) {
    Foreach ($User in $AllUsers) {
    $ObjectID = $User.ObjectID
    Write-host "`n"
    Write-Host -ForegroundColor Green "Getting Assigned Licenses for $DN"
    $GetUser = Get-AzureADUser -objectid $user.objectid
    $AssignedLicenses = ($GetUser | select -ExpandProperty assignedlicenses).skuid
    Write-Host -ForegroundColor Green "User Assigned License: " $User.Displayname "-" $AssignedLicenses "-" $User.ObjectId


    #Set Variables
    $UPN = $User.userprincipalname
    $DN = $User.Displayname
    $OBJ = $User.ObjectID
    $Age = $User.AgeGroup
    $Consent = $User.ConsentProvidedForMinor
    $Legal = $User.LegalAgeGroupClassification

        #Start foreach loop for all assigned skus
        Foreach ($License in $AssignedLicenses) {

            #Creating new PS Object for each Sku and adding to the array
            If ($TeacherSkuIDs -contains $License) {
                $TeacherObj = New-Object PSObject
                $TeacherObj | Add-Member NoteProperty -Name UserPrincipalName -Value $UPN
                $TeacherObj | Add-Member NoteProperty -Name DisplayName -Value $DN
                $TeacherObj | Add-Member NoteProperty -Name ObjectID -Value $OBJ
                $TeacherObj | Add-Member NoteProperty -Name SkuID -Value $License
                $TeacherObj | Add-Member NoteProperty -Name AgeGroup -Value $Age
                $TeacherObj | Add-Member NoteProperty -Name ConsentProvidedForMinor -Value $Consent
                $TeacherObj | Add-Member NoteProperty -Name LegalAgeGroupClassification -Value $Legal
                $TeachersArray += $TeacherObj
                if ($teachergroupid -ne $null) {
                    Add-MsolGroupMember -GroupObjectId $teachergroupid -GroupMemberType User -GroupMemberObjectId $OBJ
                }
            }
                        
            If ($StudentSkuIDs -contains $License) {
                $StudentObj = New-Object PSObject
                $StudentObj | Add-Member NoteProperty -Name UserPrincipalName -Value $UPN
                $StudentObj | Add-Member NoteProperty -Name DisplayName -Value $DN
                $StudentObj | Add-Member NoteProperty -Name ObjectID -Value $OBJ
                $StudentObj | Add-Member NoteProperty -Name SkuID -Value $License
                $StudentObj | Add-Member NoteProperty -Name AgeGroup -Value $Age
                $StudentObj | Add-Member NoteProperty -Name ConsentProvidedForMinor -Value $Consent
                $StudentObj | Add-Member NoteProperty -Name LegalAgeGroupClassification -Value $Legal
                $StudentsArray += $StudentObj
                if ($studentgroupid -ne $null) {
                    Add-MsolGroupMember -GroupObjectId $studentgroupid -GroupMemberType User -GroupMemberObjectId $OBJ
                }
            }
        }
    }
}

if ((!$teacherAdd) -and ($facultyid -ne $null)) {
    #Users to be Added in the Teacher Group that are not present
    $teacherGrpMembers = Get-MsolGroupMember -GroupObjectId $facultyid
    $teachersToAdd = ($AllUsers | ? {$_.ObjectId -ne $null}).objectid | Where {($teacherGrpMembers | ? {$_.ObjectId -ne $null}).objectid -NotContains $_}
    Foreach ($id in $teachersToAdd) {
        $GetUser = Get-AzureADUser -objectid $id
        $AssignedLicenses = ($GetUser | select -ExpandProperty assignedlicenses).skuid
        Foreach ($License in $AssignedLicenses) {

            #Adding faculty members to the security group
            If ($TeacherSkuIDs -contains $License) {
                Add-MsolGroupMember -GroupObjectId $facultyid -GroupMemberType User -GroupMemberObjectId $id
            }
        }
    }
    
    #Users (Faculty) to be removed from the group that are not in tenant anymore
    $teachersToRemove = ($teacherGrpMembers | ? {$_.ObjectId -ne $null}).objectid | Where {($AllUsers | ? {$_.ObjectId -ne $null}).objectid -NotContains $_}
    if ($teachersToRemove.Count > 0) {
        Foreach ($id in $teachersToRemove) {
            Remove-MsoLGroupMember -GroupObjectId $facultyid -GroupMemberType User -GroupmemberObjectId $id
        }
    }
}

if ((!$studentAdd) -and ($studentid -ne $null)) {
    #Users to be Added in the Student Group that are not present
    $studentGrpMembers = Get-MsolGroupMember -GroupObjectId $studentid
    $studentsToAdd = ($AllUsers | ? {$_.ObjectId -ne $null}).objectid | Where {($studentGrpMembers | ? {$_.ObjectId -ne $null}).objectid -NotContains $_}
    Foreach ($id in $studentsToAdd) {
        $GetUser = Get-AzureADUser -objectid $id
        $AssignedLicenses = ($GetUser | select -ExpandProperty assignedlicenses).skuid
        Foreach ($License in $AssignedLicenses) {

            #Adding student members to the security group
            If ($StudentSkuIDs -contains $License) {
                Add-MsolGroupMember -GroupObjectId $studentid -GroupMemberType User -GroupMemberObjectId $id
            }
        }
    }
    
    #Users (Students) to be removed the group that are not in tenant anymore
    $studentsToRemove = ($studentGrpMembers | ? {$_.ObjectId -ne $null}).objectid | Where {($AllUsers | ? {$_.ObjectId -ne $null}).objectid -NotContains $_}
    if ($studentsToRemove.Count > 0) {
        Foreach ($id in $studentsToRemove) {
            Remove-MsolGroupMember -GroupObjectId $studentid -GroupMemberType User -GroupmemberObjectId $id
        }
    }
}

Start-Transcript -Path "C:\results\log.txt"
if ($facultyid -ne $null) {
    $TeacherGroup = Get-MsolGroupMember -GroupObjectId $facultyid
    Write-Host -ForegroundColor Green "Teacher Group Count:" $TeacherGroup.Count
    Write-Host -ForegroundColor Green "Teacher Group Id:" $facultyid
}
else {
    $TeacherGroup = Get-MsolGroupMember -GroupObjectId $teachergroupid
    Write-Host -ForegroundColor Green "Teacher Group Count:" $TeacherGroup.Count
    Write-Host -ForegroundColor Green "Teacher Group Id:" $teachergroupid
}

if ($studentid -ne $null) {
    $StudentGroup = Get-MsolGroupMember -GroupObjectId $studentid
    Write-Host -ForegroundColor Green "Student Group Count:" $StudentGroup.Count
    Write-Host -ForegroundColor Green "Student Group Id:" $studentid
}
else {
    $StudentGroup = Get-MsolGroupMember -GroupObjectId $studentgroupid
    Write-Host -ForegroundColor Green "Student Group Count:" $StudentGroup.Count
    Write-Host -ForegroundColor Green "Student Group Id:" $studentgroupid
}
Stop-Transcript
```

## <a name="related-topics"></a><span data-ttu-id="e5ba9-122">相關主題</span><span class="sxs-lookup"><span data-stu-id="e5ba9-122">Related topics</span></span>

[<span data-ttu-id="e5ba9-123">指派策略給小組中的使用者</span><span class="sxs-lookup"><span data-stu-id="e5ba9-123">Assign policies to your users in Teams</span></span>](../assign-policies.md)