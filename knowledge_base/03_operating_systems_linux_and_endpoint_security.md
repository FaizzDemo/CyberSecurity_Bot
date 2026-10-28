# Operating Systems, Linux, and Endpoint Security

## 1. What Is an Operating System?

An operating system manages hardware, applications, files, users, processes, and system resources.

Examples include Windows, Linux distributions, macOS, Android, and iOS.

## 2. Users and Permissions

Operating systems use accounts and permissions to control access to files, applications, and administrative functions.

A standard user should not routinely perform all tasks with administrator or root privileges.

On Linux and other Unix-like systems, file permissions commonly include:

- Read (`r`): Read file contents or list a directory.
- Write (`w`): Modify a file or directory entries.
- Execute (`x`): Execute a program or access a directory where permitted.

Permissions should be restricted to the users and services that need them.

## 3. Essential Linux Commands

- `pwd`: Display the current directory.
- `ls`: List directory contents.
- `cd`: Change directories.
- `mkdir`: Create a directory.
- `cat`: Display file contents.
- `less`: View a file page by page.
- `cp`: Copy files.
- `mv`: Move or rename files.
- `grep`: Search text.
- `whoami`: Display the current username.
- `ps`: Display process information.
- `df -h`: Display filesystem space usage.
- `ip addr`: Show network interface information on many Linux distributions.
- `sudo`: Run an approved command with elevated privileges when configured.

Always understand a command before running it. Be especially careful with destructive commands, unfamiliar scripts, and privileged shell operations.

## 4. Processes and Services

A process is a running program.

A service is a program that provides a background function, such as web hosting or remote access.

Security practices include:
- Disable unnecessary services.
- Keep required services updated.
- Restrict exposed network services.
- Review service accounts and permissions.
- Monitor unexpected process activity.

## 5. Updates and Patch Management

Security updates often fix known vulnerabilities.

Use trusted update mechanisms, apply important patches promptly, and track devices that cannot be updated.

Organizations may test updates before widespread deployment to reduce operational disruption.

## 6. Endpoint Security

An endpoint is a device such as a laptop, desktop, or server.

Endpoint security measures include:
- Supported operating systems.
- Anti-malware protection.
- Endpoint detection and response tools.
- Host firewall rules.
- Full-disk encryption.
- Standard-user accounts.
- Application control where appropriate.
- Security updates and asset inventory.
- Protected logs and backups.

No single tool detects every threat.

## 7. Malware Types

- Virus: Malware that attaches to files or programs and spreads when they are executed or shared.
- Worm: Malware capable of spreading between systems.
- Trojan: Malicious software disguised as legitimate or useful software.
- Spyware: Software that secretly collects information.
- Ransomware: Malware commonly used to extort victims through encryption or threats of disclosure.

Malware can arrive through malicious downloads, attachments, stolen credentials, compromised websites, and vulnerable software.

## 8. Responding to Suspected Malware

1. Follow the relevant incident-response policy.
2. Isolate the device from networks when appropriate and safe.
3. Notify the responsible IT or security team.
4. Avoid entering more passwords on the affected device.
5. Preserve useful evidence and timestamps.
6. Change exposed credentials from a trusted device.
7. Recover using trusted procedures and known-good backups.

Do not destroy evidence or improvise a cleanup on an organization's device.

## 9. Backups

Backups protect against data loss caused by accidents, hardware failure, malware, and other incidents.

The 3-2-1 principle recommends keeping multiple copies, using different storage types, and maintaining an off-site copy. An isolated or immutable backup can provide additional protection.

Regularly test restoration. A backup that cannot be restored is not dependable.

## 10. System Logs

Logs record events such as logins, system errors, configuration changes, and security alerts.

Investigate:
- Repeated failed logins.
- Unexpected administrator activity.
- Unrecognized accounts.
- Unusual process behavior.
- Security tools being disabled unexpectedly.

Protect logs from unauthorized access and tampering.

## 11. Endpoint Security Checklist

- Enable security updates.
- Use strong authentication and MFA where available.
- Encrypt portable devices.
- Configure a host firewall.
- Limit administrator permissions.
- Install software from trusted sources.
- Back up important information.
- Review security alerts.
- Disable unnecessary services.
- Test recovery procedures.

## 12. Safe Practice Exercises

1. Use `pwd`, `ls`, and `whoami` in your own Linux environment.
2. Create a practice directory and list its contents.
3. Review user permissions on a test file.
4. Check the operating system's update status.
5. Write a backup and recovery checklist.

Use a disposable virtual machine for experiments that could affect the operating system.

## 13. Review Questions

1. What is the purpose of an operating system?
2. Why should standard accounts be used for everyday tasks?
3. What do `pwd` and `whoami` do?
4. Why are security patches important?
5. What should you do if malware is suspected?
6. Why must backups be tested?

## 14. Answers

1. It manages hardware, applications, files, users, and system resources.
2. Standard accounts reduce unnecessary privileges and limit potential damage.
3. `pwd` displays the current directory; `whoami` displays the current username.
4. Patches often fix known weaknesses that could otherwise be exploited.
5. Follow response procedures, isolate the device when appropriate, notify the responsible team, and preserve evidence.
6. Testing verifies that the data can actually be recovered.
