# AWS note

**Solutions Architect Associate Certification SAA-C03**

- Introduction
    
    AWS - on demand; scale easily
    
    Regions - compliance, proximity, availability, pricing
    
    availability zone - 3~6 each reagion
    
    Points of presence
    
- IAM - identity access management (global)
    
    root account - not use, not share, only for first IAM user and special task
    
    user - map physical user for AWS console
    
    group - contain users only
    
    policy - JSON (least privilege principle), inheritance, inline, custom,[user,group,role]
    (Sid, Effect, Principal, Action, Resource, Condition)
    
    password policy - 
    
    MFA - muti factor authentication (password + device)
    
    AWS CLI - command line
    
    AWS SDK - program language
    
    AWS access - management console, CLI (aws config), SDK. (access key: CLI / SDK)
    
    CloudShell - 
    
    Roles - permission for AWS service or EC2 instances to use
    
    security tool - credential report (account base); last accessed (user base)