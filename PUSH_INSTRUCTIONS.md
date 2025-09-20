# Push Instructions

## 1. Create the repository on GitHub
Go to https://github.com/OpenTraceLab and create a new repository named "OpenTraceRunners"

## 2. Push the code
```bash
cd /home/epkcfsm/src/OpenTraceRunners
git remote add origin https://github.com/OpenTraceLab/OpenTraceRunners.git
git push -u origin main
```

## 3. Validate the build
After pushing, check:
- Go to https://github.com/OpenTraceLab/OpenTraceRunners/actions
- Verify the "Build OpenTrace CI Runners" workflow runs successfully
- Check that both linux-builder and windows-builder images are created
- Verify no errors in the build logs

## 4. Test the images
Once built, test with:
```bash
# Test Linux image
docker pull ghcr.io/opentracelab/opentracerunners/linux-builder:latest
docker run --rm ghcr.io/opentracelab/opentracerunners/linux-builder:latest meson --version

# Test Windows image  
docker pull ghcr.io/opentracelab/opentracerunners/windows-builder:latest
```
